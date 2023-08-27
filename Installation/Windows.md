---
order: 10
label: Windows
---
# Windows安装

!!!警告
不要安装到任何Windows直接控制的文件夹（Program Files, System32等）。

不要以管理员权限运行start.bat。

由于Windows 7不支持NodeJS v18.16，因此无法在Windows 7上安装SillyTavern。
!!!

## 通过GitHub Desktop工具安装（最简便）
(this allows git usage **only** in GitHub Desktop, if you want to use `git` on the command line too, you also need to install [Git for Windows](https://gitforwindows.org/))
  1. Install [NodeJS](https://nodejs.org/en) (latest LTS version is recommended)
  2. Install [GitHub Desktop](https://central.github.com/deployments/desktop/desktop/latest/win32)
  3. After installing GitHub Desktop, click on `Clone a repository from the internet....` (Note: you **do NOT need** to create a GitHub account for this step)

  ![image](https://github.com/SillyTavern/SillyTavern-Docs/assets/18619528/fae5d105-449a-4e4a-b679-238347647054)

  4. On the menu, click the URL tab, and enter this URL `https://github.com/SillyTavern/SillyTavern` and click Clone. You can change the Local path to change where SillyTavern is going to be downloaded.

  ![image](https://github.com/SillyTavern/SillyTavern-Docs/assets/18619528/6bdded9b-e182-4cac-89ff-e4727dbb97b2)

  6. To open SillyTavern, use Windows Explorer to browse into the folder where you cloned the repository. By default, the repository will be cloned here: `C:\Users\[Your Windows Username]\Documents\GitHub\SillyTavern`
  
  7. Double click on the `start.bat` file. (Note: the `.bat` part of the file name might be hidden by your OS, in that case it will look like a file called "`Start`". This is what you double-click to run SillyTavern)

  ![image](https://github.com/SillyTavern/SillyTavern-Docs/assets/18619528/a77b8bc2-72a9-42a9-8aa9-1ed89f9bbf35)

  8. After double-clicking, a large black command console window should open and SillyTavern will begin to install what it needs to operate.
  
  9. After the installation process, if everything is worked, the command console window should look like this and a SillyTavern tab should be open in your browser:

  ![image](https://github.com/SillyTavern/SillyTavern-Docs/assets/18619528/d9da4608-94cd-447c-bde2-7f0f9de1c2eb)

  10. Connect to any of the [supported APIs](https://docs.sillytavern.app/usage/api-connections/) and start chatting!

## 通过Git安装

  1. Install [NodeJS](https://nodejs.org/en) (latest LTS version is recommended)
  2. Install [Git for Windows](https://gitforwindows.org/)
  3. Open Windows Explorer (`Win+E`)
  4. Browse to or Create a folder that is not controlled or monitored by Windows. (ex: C:\MySpecialFolder\)
  5. Open a Command Prompt inside that folder by clicking in the 'Address Bar' at the top, typing `cmd`, and pressing Enter.
  6. Once the black box (Command Prompt) pops up, type ONE of the following into it and press Enter:

- for Release Branch: `git clone https://github.com/SillyTavern/SillyTavern -b release`
- for Staging Branch: `git clone https://github.com/SillyTavern/SillyTavern -b staging`

  7. Once everything is cloned, double click `Start.bat` to make NodeJS install its requirements.
  8. The server will then start, and SillyTavern will popup in your browser.

## 通过下载zip压缩包安装（不推荐）

  1. Install [NodeJS](https://nodejs.org/en) (latest LTS version is recommended)
  2. Download the zip from this GitHub repo. (Get the `Source code (zip)` from [Releases](https://github.com/SillyTavern/SillyTavern/releases/latest))
  3. Unzip it into a folder of your choice
  4. Run `Start.bat` via double-clicking or in a command line.
  5. Once the server has prepared everything for you, it will open a tab in your browser.
