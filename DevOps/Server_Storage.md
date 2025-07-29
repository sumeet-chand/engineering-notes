

SERVER STORAGE SETUP


1. Buy the Hardware
Server: Dell PowerEdge R740xd / HP ProLiant DL380 / SuperMicro (12+ bays).
Disks:
HDDs: Seagate IronWolf 8TB+ (NAS) / WD Gold (enterprise).
SSDs: Samsung PM893 (SATA) / Kioxia CM6 (NVMe for cache).
RAID Card: LSI MegaRAID 9460-8i (hardware RAID) or HBA (for ZFS).
Extras:
UPS (APC 1500VA)
10Gbps NIC (Intel X550)

2. RAID Setup
Boot into RAID card BIOS (Ctrl+R during POST).
Create Virtual Disk:
RAID Level: 10 (performance) or 6 (capacity).
Strip Size: 256KB (general use) / 1MB (large files).
Enable Cache: Write-back + BBU (battery).

3. Install OS
For Windows:
Boot from USB → Install Server 2022 → Enable Storage Spaces.
For TrueNAS:
Flash USB installer → Install to 2x mirrored boot SSDs → Select pool disks.

4. Configure Storage
Windows (Storage Spaces)
powershell
# Create pool  
New-StoragePool -FriendlyName "NAS" -StorageSubsystemFriendlyName "Windows Storage*" -PhysicalDisks (Get-PhysicalDisk -CanPool $true)  

# Create virtual disk (RAID-5 equivalent)  
New-VirtualDisk -StoragePoolFriendlyName "NAS" -FriendlyName "Data" -ResiliencySettingName "Parity" -Size 20TB  
TrueNAS (ZFS)
bash
# Create pool (RAID-Z2 = RAID-6)  
zpool create -f tank raidz2 /dev/disk1 /dev/disk2 /dev/disk3 /dev/disk4  

# Enable compression  
zfs set compression=lz4 tank  

5. Create Shares
Protocol	Windows	TrueNAS
SMB	New-SmbShare -Name "Data" -Path "D:\Data"	Web UI → Shares → SMB → Add Path
NFS	Install-WindowsFeature NFS-Client	Web UI → Shares → NFS → Add Export

6. Secure It

Permissions:
Windows: icacls D:\Data /grant "DOMAIN\Users:(OI)(CI)(RX)"
TrueNAS: chmod -R 770 /mnt/tank/data

Backups:
bash
# Linux/TrueNAS  
rsync -avz /mnt/tank/data backup-server:/backups  
powershell
# Windows  
robocopy D:\Data \\backup-server\Data /MIR /R:1 /W:1  

7. Monitor
SMART Checks:

bash
smartctl -a /dev/sda | grep "Reallocated\|Temperature"  
Email Alerts:

TrueNAS: Web UI → System → Email
Windows: Set-SMTPConfig -Server "smtp.yourdomain.com" -From "nas@bobsbuilders.com"

