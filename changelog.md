## Change Log:
- 1.9.11
Fix for mountify

- 1.9.10    
Now patch the real xml (pattern bug patch all)
Fixed symlink inside symlink folder
Change find logic to work only on /modules folder

- 1.9.9     
Improved partition handling and expanded OEM partition support for better compatibility
Cleaned up and simplified XML patching logic
Fixed encoding issues in reboot messages
Improved Doze persistence across reboots
Enhanced GMS whitelist removal on newer Android versions
Fixed debug log path
Reduced unnecessary patching and false warning messages
Improved uninstall cleanup and restoration behavior

- 1.9.8     
Added a method to force patch on oneplus devices (and others?), thanks to @xizt159

- 1.9.7   
Add gsf to whitelist (possible notification fix)
{Debug zip} Added more debug logs and another way to mount to try get work on OOS

- 1.9.6   
Added more tags to find and patch GMS
Added webui option to add apps for a new delay fix

- 1.9.5   
Updated uninstall.sh to add clear cache
Added debug zip

- 1.9.4   
Added WebUI with GMS Patch status, Fix Delayed Messages, Find My Device toggle, and Force Re-apply Optimization

- 1.9.3   
Fixed KernelSU compatibility (dynamic busybox path resolution)
Fixed shebang in all scripts (removed hardcoded Magisk busybox path)
Fixed syntax error in uninstall.sh
Fixed quote bug in GMS0 variable across scripts
Fixed loose product/ directory not merging into system/ on install
Added APatch explicit support in customize.sh
Added fallback stubs for ui_print/abort/set_perm in customize.sh
Added CRLF to LF conversion requirement for Windows builds (see build.ps1)
Reduced boot completion polling interval (100s → 10s)
Updated gmsc whitelist parser for Android 15+ output format
Updated updateJson to point to fork repository
Known issue: KernelSU 3.x (32302+) requires meta-overlayfs or another metamodule to be installed first, otherwise modules will not mount. This is by design in KernelSU 3.x.

- 1.9.2   
Android 15 support   
Improved root implementations (Support Magisk / KernelSU / APatch)   
Improved XML dir/path detections (73Sydney)   
Clear old GMS data on first install   

- 1.9.1   
Improved installation (Magisk Live and KernelSU)   
Fixed root method detections   
Fixed uninstaller script   

- 1.9.0   
Android 14 support      
Fixed synchronization for Location Sharing and Play Games   

- 1.8.8   
A long-awaited hotfix   
Addresses script that caused patching XML gone wrong   
Raised Magisk Boot Service to 100 seconds   

- 1.8.7   
Android 13 support   
Added GMS to battery optimization and disabled another components   
Fixed broken API checking and Multi-User support   
Moved to inbuilt (Magisk) BusyBox   
Improved pre-boot conflict fixer and proper boot script execution   
Improved superuser checking method and used cmd flag arguments   
Improved XML patching logic   
Minimized root path checking depth   
Revived overall code quality and syntax   
Rewrite GMS state checker bin   

- 1.8.6   
Added /system_ext detection support   
Improved patching detections (Allow to revoke location permissions)   

- 1.8.5   
Added updateJson support   
Improved patching detections (XML files)   

- 1.8.4   
Removed redundant script (GMS: Stay with disabling Find My Device only)   

- 1.8.3   
Android 12 support   
Additional boot complete check   
Multi-User support   
Set ignore for GMS and IMS WRITE_SETTINGS   
Minor improvements   

- 1.8.2   
Android 11 support   
Improved installation (Magisk Live and Custom Recovery)   
Improved patching detections (XML files and conflicting modules)   
Integrated add-on (run 'gmsc' with superuser rights for check optimization status)   
Set ignore for GMS and IMS BOOT_COMPLETED   
Set ignore for GMS and IMS AUTO_START (custom permissions for Oxygen OS)   
Updated template   

- 1.8.1   
Integrated custom recovery installation   
Added boot logic for search and patch any conflicting modules (if present)   
Whitelisted IMS and Turbo (this should fixed location crash issue in MIUI)   

- 1.8.0   
Initial re-release   
100 seconds Magisk Boot Service   
