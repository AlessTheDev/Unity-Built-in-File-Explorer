# Unity-Built-in-File-Explorer
![File Explorer Preview](https://github.com/AlessTheDev/Unity-Built-in-File-Explorer/blob/main/github/preview.png?raw=true) <br/>
This is an unity built in file explorer I made for my game, it has basic features like changing path, select files, shortcuts and filters
## Get Started
1. First of all, [download the package zip file](https://github.com/AlessTheDev/Unity-Built-in-File-Explorer/blob/main/FileExplorerPackage.zip) and extract it
2. Open the unity package manager andselect the option "Add project from disk", then select the package.json file from the unzipped folder
   <br/> ![package manager](https://github.com/AlessTheDev/Unity-Built-in-File-Explorer/blob/main/github/package-manager.png?raw=true)
3. Wait until the installation is completed
## Set Up
1. Now that we have installed the package in the project let's drag the **FileExplorer** prefab from the Package folder
![Package folder](https://github.com/AlessTheDev/Unity-Built-in-File-Explorer/blob/main/github/package-folder.png?raw=true)
2. Now add the camera to the canvas and add the UI **Event system**
3. Create an initializer script:
   ```
   public class FileExplorerTest : MonoBehaviour
   {
       void Start()
       {
           FileExplorerManager.Instance.Hide(); //IMPORTANT (Initialize the instance, the gameobject must be active)
           FileExplorerManager.Instance.Show(); //Call this when you want it to pop up
       }
   }
   ```
5. Everything should work!
## Get the selected file
Create a script and add a function to handle the selected file, you can access the file path and name
```
   public void HandleSelectedFile()
       {
           Debug.Log("A file has been selected! " + FileExplorerManager.Instance.GetSelectedFile().filePath);
       }
```
Add the function to the event system <br/>
![On file selected](https://github.com/AlessTheDev/Unity-Built-in-File-Explorer/blob/main/github/on-file-selected.png?raw=true)
## Costumize
To costumize the explorer settings go to the FileExplorer gameobject
### Extension filter
![Settings](https://github.com/AlessTheDev/Unity-Built-in-File-Explorer/blob/main/github/settings.png?raw=true) <br/>
This array defines all the allowed extensions, the other files will be ignored, leane the array blank to allow all files extensions
### Close button
A boolean shows/hides the close button (in case a user MUST select a file)
### Icons
![Icons](https://github.com/AlessTheDev/Unity-Built-in-File-Explorer/blob/main/github/icons.png?raw=true) <br/>
In the FileExplorer gameobject you should be able to find the FileIcons script where you can decide the icons
