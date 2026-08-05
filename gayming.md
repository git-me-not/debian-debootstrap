# For gayming purpose
1. Create a new user \
```doas /sbin/useradd -m $gayming_user``` \
```doas /sbin/usermod -aG video,audio,render $gayming_user``` 
2. Log in to the new user
3. Install Steam (cek steam.md yah)
4. Done

# Security purpose
I have a multi-purpose subvol to store all my data, including the Steam library.
I definitely don't want my gayming-only user to have access to all my data,
so this is the solution, kinda. \
\
From main user:
1. Making the mount point of the subvol \
```doas mkdir /media/Storage```
2. Set the permission so every account can "access" it without being able to browse the content \
```doas chown root:root /media/Storage``` \
```doas chmod 711 /media/Storage```
3. Create a directory to store my private data \
```mkdir /media/Storage/data```
4. Set the permission of the directory and everything inside \
```doas chown -R $main_user:$main_user /media/Storage/data``` \
```doas chmod 700 /media/storage/data``` 
5. Create a directory to store my gayming data \
```mkdir /media/Storage/SteamLibrary```
6. Set the permission of the directory and everything inside \
```doas chown -R $gayming_user:$gayming_user /media/Storage/SteamLibrary``` \
```doas chmod 700 /media/storage/SteamLibrary```
7. Done
\
\
Note: \
711 : Owner can do anything with the file and directory, other users can only execute it (can access but not browse). \
700 : Owner can do anything with the file and directory, other users can't do anything at all.
