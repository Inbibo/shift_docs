# fileSystem
A catalog to work with the OS filesystem and environment variables. It includes operators to perform file & directory creation and manipulation and more.

## *fileSystem* Operators
## CopyFiles


<figure style="width: 30%">
	<img src="images\CopyFiles.png" alt="Node UI">
</figure>


Operator to copy a given list of files to a target directory.
    By turning on the preserveMetadata option one can choose to also copy the file's metadata.
    Optionally one can specify to create the target directory if the one provided does not exist.
    If the skipOnError option is on, the copying process will continue and will show a warning if an error occurs. If it's off it will stop the copy and raise an error. 
    If the overwrite option is on, the copying process will overwrite the existing files and will show a warning message. If it's off it will ignore the existing files.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| filesPaths | List | []
| directory | Dir | 
| preserveMetadata | Bool | True
| createPath | Bool | False
| skipOnError | Bool | False
| overwrite | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| copiedFiles | List | []


## CreateDirectory


<figure style="width: 30%">
	<img src="images\CreateDirectory.png" alt="Node UI">
</figure>


Operator to create a directory in the provided path.
    Optionally one can specify to create the path if the one provided does not exist.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| directoryName | String | ""
| pathName | Dir | 
| createPath | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| directoryPath | Dir | 


## CreateTempDirectory
<span style="color: yellow"><i>Beta operator</i></span>


<figure style="width: 30%">
	<img src="images\CreateTempDirectory.png" alt="Node UI">
</figure>


Operator to create a temporary directory in the provided path.
     If no path is provided it will use the default temp directory.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| pathName | Dir | 
| prefix | String | ""
| suffix | String | ""
| createPath | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| directoryPath | Dir | 


## FilterFiles


<figure style="width: 30%">
	<img src="images\FilterFiles.png" alt="Node UI">
</figure>


Filter a list of files using either Python regular expressions format or a shell style matching.
    By turning the onlyBasename option on, the filter will only filter by the basename of the provided files.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| files | List | []
| regex | String | ""
| shellStyle | Bool | False
| onlyBasename | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| filteredFiles | List | []


## GetCurrentDirectory


<figure style="width: 30%">
	<img src="images\GetCurrentDirectory.png" alt="Node UI">
</figure>


Operator to get the current working directory path.
    Optionally one can specify to get the absolute or the relative path.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| relativePath | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| directoryPath | Dir | 


## GetEnvironmentVariable


<figure style="width: 30%">
	<img src="images\GetEnvironmentVariable.png" alt="Node UI">
</figure>


Operator to get the value of the environment variable provided.
    If the variable does not exist, the node returns None.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| name | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| value | String | ""


## GetPythonSysPath


<figure style="width: 30%">
	<img src="images\GetPythonSysPath.png" alt="Node UI">
</figure>


Operator to get the content stored in the sys.path variable. Returns a list of strings.
    
    

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| pythonSysPath | List | []


## JoinPath


<figure style="width: 30%">
	<img src="images\JoinPath.png" alt="Node UI">
</figure>


Operator to join the two given paths.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| mainPath | Dir | 
| addPath | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| resultPath | String | ""


## ListDirectory


<figure style="width: 30%">
	<img src="images\ListDirectory.png" alt="Node UI">
</figure>


Operator to list all content inside a given directory path. 
    If requested full paths, it updates the paths to include the directory.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| directoryPath | Dir | 
| fullPaths | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| content | List | []


## MakeAbsolutePath


<figure style="width: 30%">
	<img src="images\MakeAbsolutePath.png" alt="Node UI">
</figure>


Operator that gets the absolute path of the provided path.
    Optionally one can specify the base directory to the absolute path, by default it is absolute to the current working directory.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| path | String | ""
| baseDirectory | Dir | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| absolutePath | Dir | 


## MakeRelativePath


<figure style="width: 30%">
	<img src="images\MakeRelativePath.png" alt="Node UI">
</figure>


Operator that gets the relative path of the provided path.
    Optionally one can specify the base directory to the relative path, by default it is relative to the current working directory.
    The provided path has to be an absolute path, if not then it will raise an error.
    The path and the base directory have to belong to the same mounted disk in the system.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| path | Dir | 
| baseDirectory | Dir | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| relativePath | String | ""


## MoveFiles


<figure style="width: 30%">
	<img src="images\MoveFiles.png" alt="Node UI">
</figure>


Operator to move a given list of files to a target directory.
    By turning on the preserveMetadata option one can choose to also preserve the file's metadata.
    Optionally one can specify to create the target directory if the one provided does not exist.
    If the skipOnError option is on, the moving process will continue and will show a warning if an error occurs. If it's off it will stop the moving process and raise an error. 
    If the overwrite option is on, the moving process will overwrite the existing files and will show a warning message. If it's off it will ignore the existing files.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| filespaths | List | []
| directory | Dir | 
| createDirectory | Bool | False
| preserveMetadata | Bool | True
| skipOnError | Bool | False
| overwrite | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| movedFilepaths | List | []


## ReadFile


<figure style="width: 30%">
	<img src="images\ReadFile.png" alt="Node UI">
</figure>


Operator to read the content from a given file.
    Optionally the reading mode can be modified. By default it is on reading mode.
    The default encoding is utf-8, this can be updated by changing the encoding option.
    
    

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| file | FileIn |  | 
| readMode | Enum | Default | Default, Binary
| encoding | String | "utf-8" | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| fileContent | String | ""


## ReadFileLines


<figure style="width: 30%">
	<img src="images\ReadFileLines.png" alt="Node UI">
</figure>


Operator used to read the content from a given file line by line.
    The result is a list of strings where each element of the list represents one line in the file.
    Optionally the reading mode can be modified to support binary content.
    The default encoding is utf-8, this can be updated by changing the encoding option.
    
    

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| file | FileIn |  | 
| readMode | Enum | Default | Default, Binary
| encoding | String | "utf-8" | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| fileLines | List | []


## RemoveDirectory


<figure style="width: 30%">
	<img src="images\RemoveDirectory.png" alt="Node UI">
</figure>


Operator to remove the given directory. By default, if the directory is not empty, the operator will raise an error.
    Optionally one can force the recursive removal of its content by turning on the removeContent option.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| directoryPath | Dir | 
| removeContent | Bool | False

## RenameFiles


<figure style="width: 30%">
	<img src="images\RenameFiles.png" alt="Node UI">
</figure>


Operator to rename a given list of filepaths with the new names provided by the newFilenames list.
    If the option overwrite is on and the name of the new file already exists, then it will be overwritten. Otherwise it will show a warning about the filename being duplicated.
    If the option skipOnError is on and an error occurs while renaming a file, the execution will continue to the next filepath. Otherwise it will raise an error and stop.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| oldFilepaths | List | []
| newFilenames | List | []
| overwrite | Bool | False
| skipOnError | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| outFiles | List | []


## SetCurrentDirectory


<figure style="width: 30%">
	<img src="images\SetCurrentDirectory.png" alt="Node UI">
</figure>


Operator to set the current working directory to the path specified.
    If the createPath option is turned on and the path provided does not exist, it will be created.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| directoryPath | Dir | 
| createPath | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| currentDirectory | Dir | 


## SetEnvironmentVariable


<figure style="width: 30%">
	<img src="images\SetEnvironmentVariable.png" alt="Node UI">
</figure>


Operator to set the value of an environment variable.
    If the environment variable already exists, it will be overwritten.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| name | String | ""
| value | String | ""

## SetFileExtension


<figure style="width: 30%">
	<img src="images\SetFileExtension.png" alt="Node UI">
</figure>


Operator to set an extension to a given filename.
    Optionally one can turn on the replaceExtension option if the filepath already has an extension, this will replace it with the provided one.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| filepath | FileIn | 
| extension | String | ""
| replaceExtension | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| newFilepath | String | ""


## SplitFileExtension


<figure style="width: 30%">
	<img src="images\SplitFileExtension.png" alt="Node UI">
</figure>


Operator to split a given filename into the root filename and the extension.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| filename | FileIn | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| root | String | ""
| extension | String | ""


## SplitFilePath


<figure style="width: 30%">
	<img src="images\SplitFilePath.png" alt="Node UI">
</figure>


Operator that splits the given filepath in two parts: directory contains the last pathname component and basename contains everything leading up to that.
    
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| filepath | FileIn | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| directory | String | ""
| basename | String | ""


## WriteFile


<figure style="width: 30%">
	<img src="images\WriteFile.png" alt="Node UI">
</figure>


Operator to write the given content to the provided file.
    Optionally one can turn on the createFile if the provided file does not exist. Otherwise it will raise an error.
    Optionally the writing mode can be modified. By default it is on writing mode(w).
    
    

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| file | FileIn |  | 
| contents | String | "" | 
| writeMode | Enum | Overwrite | Overwrite, Extend, Binary Overwrite, Binary Extend
| encoding | String | "utf-8" | 
| createFile | Bool | False | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| writtenFile | FileOut | 


## WriteFileLines


<figure style="width: 30%">
	<img src="images\WriteFileLines.png" alt="Node UI">
</figure>


Operator to write the given list of strings to the provided file as individual lines.
    Optionally one can turn on the createFile if the provided filename does not exist. Otherwise it will raise an error.
    Optionally the writing mode can be modified. By default it is on overwriting mode.
    The default encoding is utf-8, this can be updated by changing the encoding option.
    
    

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| file | FileIn |  | 
| contents | List | [] | 
| writeMode | Enum | Overwrite | Overwrite, Extend, Binary Overwrite, Binary Extend
| createFile | Bool | False | 
| encoding | String | "utf-8" | 

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| writtenFile | FileOut | 


