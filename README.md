# React_Notes

# None of your business  

1. Revise prevoius lesson
2. What are bundlers- vite, parcel, webpack-->?
3. find the difference btw them?
   4.what is npm and yarn?
   5.npm doesnt statnd for node package manager(see doc)?

6.how 'npm inti' works?
-> Its created a package.json file for the project.

7. Useing 'parcel' webpack?

8.if we only want to use parcel during development not production?
->npm install parcel (production, when we want it globally)
npm install -D parcel (developement, here D is for dev dependencies)
npm install --save-dev parcel (development, same)

dev dependencies are those that our project needs for development, eg:- parcel.

9. learn about ^(caret) and ~(tilde) in packages ?
10. package without these sign means, they want to use this specific version?
    11.About package-lock.json?
    -> Its a very important file
    its lock the version
    never put it in git ignore
    It stores the exact version of the dependencies used in project

It have integraty field- stores the hash to check the version is same on production or not

Note:- when we face issues as its the code is working on my local but not on production then there is a version issues with the package file. The package -lock .json file is not pushed in server.

12. what is hash? what is the meaning of the code written in package.lock ?

our application is dependent on dev dependencied, they dependent on parcel like things, they also dependent on node modeule, node modules have different library eg:-
browserlist - make our app run on old browsers

13. We never push node modules in git as its very heavy and our package.lock.json has sufficient information to recreate it. As package.lock file maintain everything from package to exact version

14. Why creating react app from command is best ?
    -> Beacuse it can automatically update its version from server
    Now here we are fetching react through CDN but when insatlled then, react is on our server.
    So, fetching data from our server is more fast than fetch form CDN.
    Our server has node modules, and these modules has react.

15. In package.json we have:-

devDepencies -- dependencies for developement purpose, its not present in production

dependencies -- Its present globally(development + production)

16. what does babel do?
17. How create-react-app works?
18. diff btw npm and npx?
19. Command that we ran during creating a react application?
    ->1. npm init
    Ask certain questions and create package.json file
20. npm install -D parcel
    After running this command the, we get package.lock json file.
    As any command that install package will create a package.lock.json file for storing data of that package.
    Here "-D" means that this package is used for development purpose.

21. Why we need "npm" in our project?
    -> Because npm manages packages, and we need packages for our project to run.
    Our react app is powered by a lots of packages eg;- to run, for minification, etc, for these we need helper packages, which we get from npm.

22. npx means "execute using npm"

23. Now, we do install pacel:- npx parcel index.html
    As index.html is the starting point in our application.
    parcel craete a build and deploy in local server

24. Never touch node-modules and package.lock.json

24.what is type in script tag?

25. When we save changes in file, then automatically the server reloads and show the changes?
    --> This functionality is called live server, but not all live server have this function.
    Parcel is doing this live server thing. Its called as Hot Module Reload (HMR).
    Parcel uses "file watcher algorithms" for this functionality, its written in C++

26. Parcel creates .parcel-cache file for its use.

27. for production build:- npx parcel build index.html

    It create a minified build for production and stores in .dist folder
    Here, we have to remove " "main": "App.js", " from package.json as we have given the entry point of app in command

28. what parcel is doing?
    -> HMR - Hot Module Reloading  
    File Watcher Algorithms - C++
    Bundling
    Minify
    Cleaning our code

29. Production build takes more time than development build, as its more minified
