## Paths
### Relative
This is the path relative from where you are:
If you are in JMS, the path would just be `/407`
### Absolute
This is the exact path so you can get from anywhere:
`Scotland/UofG/JMS/407`
## Syntax
```java
// Verify existence
Files.exists(Path);
Files.notExists(Path);
// Check accessibility
Files.isReadable(Path);
Files.isWritable(Path);
Files.isExecutable(Path);
// Do two Paths locate the same file?
Files.isSameFile(Path, Path);
Files.delete(Path);
Files.deleteIfExists(Path);
// Doesn’t throw an Exception even if file doesn’t exist
Files.copy(Path, Path);
Files.move(Path, Path);
Files.createFile(Path)
// Throws an Exception if file already exists, or if parent
// directory does not exist
Files.createDirectory(Path)
// Throws Exception if directory already exists, or if parent 
// directory does not exist
Files.createDirectories(Path)
//Creates all necessary directories from the top down
```