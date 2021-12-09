# Usage

This example allows you to set credentials and access your Blob storage.

```
DefaultFileSystemManager defaultFileSystemManager = new DefaultFileSystemManager();
VFS.setManager(defaultFileSystemManager);
defaultFileSystemManager.addProvider(AzConstants.AZSBSCHEME, new AzFileProvider());
defaultFileSystemManager.init();

StaticUserAuthenticator auth = new StaticUserAuthenticator("", "<storage-account-name>",
        "<storage-account-key>");
FileSystemOptions opts = new FileSystemOptions();
DefaultFileSystemConfigBuilder.getInstance().setUserAuthenticator(opts, auth);

FileObject fileObject = defaultFileSystemManager.resolveFile(
        AzConstants.AZSBSCHEME + "://<storage-account-name>.blob.core.windows.net/<container>/<file>.<ext>", opts);
```
