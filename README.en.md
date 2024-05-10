# Working on a project with command line and github
## In Computer

in the computer, decide a Folder location for the projects.
Open the folder, or, open the Bash and navigate to that folder

Navigate to the destination
```bash
cd destination
```

Create a folder for the project
```bash
mkdir myproject
```

Navigate to the project folder
```bash
cd myproject
```
Open VSCode
```bash
code .
```

Now we have the project opened in VSCode

## In VSCode
Initiate a git repository **Locally**
```bash
git init
```
Now we started a git repository
The first branch may be named master, to rename to main we can do
```bash
git branch -m master main
```

### Creating some files

With the command ```touch``` we can create files, give a name and the extension, lets create a index.html file
```bash
touch index.html
```
Create a CSS file
```bash
touch style.css
```

If we need to organize the files we can create a folder, for example
```bash
mkdir css
```
That command above will create a folder called css, and now we can move the css file inside that folder with
```bash
mv style.css css
```

## creating an html template
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

Once we created what is needed as the **BASE** for our project, we can commit the base of this project

## Adding, Commiting, Creating a repository from command line or VSCode
As we already did ```git init``` on the beginning, now we can add and commit, but we still need to create a repository on github.com

The steps
to add everything
```bash
git add .
```
or to add just a specific file
```bash
git add index.html
```
Then we commit our changes
```bash
git commit -m "The description that we want"
```
Now we need to create our repository so that we can upload our changes.

**Creating a repository from the computer/ vscode**

We need to have the Git CLI installed in order to be able to do that
After it is installed we can use the following command to create a repository online

```bash
gh repo create name
```
This is the first part of the command
it calls github ```gh``` and repository ```repo``` to create and we give a name to our repository ```name```

We also need to tell to github if we want the repository to be **PUBLIC** or **PRIVATE**, as well a Description for our repository

We can do that with flags on the command that we have above

- ```--public``` sets the repository to public
- ```--private``` sets the repository to private
- ```--description "text"``` sets the repository description

the **FULL** command should look like this
```bash
gh repo create myproject --public --description "My Project Repository"
```
Now we might need to add the remote Origin, this means, we are telling Git on our computer, where does the repository ( live ) in github

```bash
git remote add origin https://github.com/our-username/our-repo-name.git
```

Now that we did initiate the repository, added the remote origin, we can now upload our changes to our online github repository with the command
```bash
git push -u origin main
```
- NOTE: ```main``` in our case is the name of our branch that we are uploading the code to.

the next uploads would be a simple
```bash
git push
```

## Different branches
when we create a new branch, and we are done with the code, and if we need to upload the code to github before we ```merge```
We need to set a new ```Origin```
So we repeat the steps of adding and commiting our changes
```bash
git add .
git commit -m "Our message"
```
and then we set a **New Origin**
```bash
git push --set-upstream origin branch-name
```

After we completed this step, we can freely ```push``` changes in the future without the need to set the upstrea, with the command
```bash
git push
```