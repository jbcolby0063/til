# package-lock.json

```package-lock.json``` file keeps track of the exact version of packages that are installed.

This way, a product is reproducible in the same way even if the packages are updated.

This solves the problem that ```package.json``` has. 

In ```package.json```, it uses ```version range``` to set which versions you want to 
upgrade to (patch or minor). 

So when you trying to copy the project in another computer using ```npm install```, it will install 
different version of a package if the patch or minor of that package has been released. 

For example, let's say there is a project that contains a ```package.json``` file with express package of "^4.16.3"(^ = patch and minor releases update) version range. And when there was a new minor release for the package and you try to replicate the same project in another computer using ```npm install```, it will install different versions like "4.16.4" or "4.17.1". So the original project and the newly initialized project are actually different. 

However, ```package-lock.json``` sets the versions of each installed packages in stone, and ```npm``` will use those exact versions when running ```npm install```. 

This way, every machine will be able to run the project in the same environment and same dependencies.

Therefore, the ```package-lock.json``` file needs to be committed to your Git repository, so it can be fetched by other people. 
