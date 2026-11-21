# [FIX] How to Restore Offline Mode in SKlauncher 4.0.58 (Windows)
## The Problem
In SKlauncher version 4.0.58, the option to add an offline account disappeared from the login screen. Instead, the launcher only displays the Microsoft account login option.
<img width="1080" height="602" alt="image" src="https://github.com/user-attachments/assets/744e100c-ce2d-4210-bb5d-8936916b898b" />
The workaround is to manually add an offline profile to the accounts.json file.

## Tutorial
### 1. Open the SKlauncher folder
Press Win + R, type:

`%appdata%\.sklauncher`
Then press Enter.

### 2. Create the accounts.json file
<img width="724" height="498" alt="image" src="https://github.com/user-attachments/assets/d81f27c9-26b5-40fc-b88c-7235d08becec" />

If `accounts.json` doesn't already exist, you can create it manually

Right-click an empty area inside the folder.

Select New → Text Document.

Rename it to `accounts.json`.

Important: Make sure the filename isn't `accounts.json.txt`.

### 3. Get your UUID
Visit:

https://skmedix.pl/settings

Log in to your SKlauncher account and locate your profile UUID. (If you don’t have an account, create one; it’s easy and free)
<img width="1080" height="360" alt="image" src="https://github.com/user-attachments/assets/e495b46b-8e69-4949-a7af-8a04cf643c68" />


4. Edit accounts.json
Open the file with Notepad and paste the following content:

```{
  "accounts": [
    {
      "id": "YOUR_USERNAME",
      "type": "offline",
      "username": "YOUR_USERNAME",
      "uuid": "YOUR_UUID"
    }
  ],
  "activeAccountId": "YOUR_USERNAME"
}
```

Replace:

`YOUR_USERNAME` with your SKLauncher's username.

`YOUR_UUID` with the UUID found in your SKlauncher account settings.

Important: Keep `type` set to `offline`. Both `id` and `activeAccountId` must match your SKlauncher username.

## 5. Save and restart SKlauncher
Save the file, close Notepad, and launch SKlauncher again.

Your offline profile should now appear!

<img width="1080" height="607" alt="image" src="https://github.com/user-attachments/assets/fe277239-a1da-4a75-9cf2-5d7de8e1a9ac" />

## Additional Information
Tested launcher version: SKlauncher 4.0.58.

Operating system: Windows 11.

Tested workaround: Manually creating accounts.json.

No need to reinstall SKlauncher or Minecraft.

Note: This is a community workaround, not an officially confirmed fix from the developers. It was also done using ChatGPT and its search capabilities; it might not work for others or in version 3.2, but it’s what worked for me.
