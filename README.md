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
30. what are react lifecycle and how to implement them in functional react?
# React component lifecycle:-
1. componentDidMount 
-> This is the first lifecycle of a React component, this is the stage where the component is created and inserted into the DOM

2. Updating
 shouldComponentUpdate and the componentDidUpdate

The shouldComponentUpdate lifecycle method is very simple. We should just return a boolean to determine if the component
 React should update the component. The default value for this method is true.

The componentDidUpdate lifecycle method is invoked after the update happens in the component. This lifecycle method is 
used to compare if a specific prop or state has changed.

3. Unmouting
componentWillUnmount-> This lifecycle method will be invoked when the component is about to be removed from the DOM

# Deprecated Methods:-
componentWillMount
componentWillReceiveProps
componentWillUpdate

# React 17.0 version lifecycle were removed completely.

# Lifecycle hooks in functional React:-

1. useEffect Hook as componentDidMount, componentDidUpdate, and componentWillUnmount combined.

i) componentDidMount:-

This is how we can perform the equivalent of componentDidMount using the useEffect Hook:

 useEffect(() => {
  // Inside this callback function we perform our side effects.
});

Just calling the useEffect Hook and passing the callback function, we’re performing the equivalent of the componentDidMount lifecycle method. Very easy.

ii) componentDidUpdate

To perform the equivalent of the componentDidUpdate using the useEffect Hook, we should do this:

useEffect(() => {
  // Inside this callback function we perform our side effects.
}, [dependency]);

That’s it. It’s almost the same as the previous one, but this time we’re passing our array of dependencies as the second parameter, and inside that array, we should pass the dependency that we want to watch. If you don’t pass any dependency, the useEffect Hook will still work as the componentDidUpdate lifecycle method.

iii) componentWillUnmount

To do the cleanup after the component unmounts, we have a simple way to perform the equivalent of the componentWillUnmount using the useEffect Hook.

The only thing that we need to do is to return a function inside the callback function of the useEffect Hook, like this:

useEffect(() => {
  window.addEventListener("mousemove", () => {});
  return () => {
    window.removeEventListener("mousemove", () => {})
  }
}, []);

That’s it. It’s very simple, we can use the useEffect Hook to perform side effects similar to the lifecycle methods that we have in class components, and with clean and straightforward code.


# Third Day 

1. Revise prevoius lesson
2. What are bundlers- vite, parcel, webpack-->?
-> React uses different bundlers like, webpack, browserfy, rollup and Parcel.
    Bundler does a lot of things to optimize the react code
    1. Code Splitting
    2. React.lazy

3. find the difference btw them?
4.what is npm and yarn?
5.npm doesnt statnd for node package manager(see doc)?

6.how 'npm inti' works?
-> Its created a package.json file for the project.

Try:- npm init -y, what it does?

7. Useing 'parcel' webpack?

8.  if we only want to use parcel during development not production?
->npm install parcel (production, when we want it globally)
   npm install  -D parcel (developement, here D is for dev dependencies)
   npm install  --save-dev parcel (development, same)

  dev dependencies are those that our project needs for development, eg:- parcel.

9. learn about ^(caret) and ~(tilde) in packages ?
-> version syntax:- Major.Minor.Patch

    1. The ~1.2.0 will update all the future patch updates. We have to write just ~1.2.0 and all the next patch update dependencies. For example, 1.2.1, 1.2.2, 1.2.5……………1.2.x.
    It gives you bug fix releases.

    2.The ^1.2.4 will update all the future Minor and patch updates, for example, ^1.2.4 will automatically change the dependency to 1.x.x if any update occurs. 
    It gives you backwards-compatible new functionality as well.


10. package without these sign means, they want to use this specific version?
11.About package-lock.json?
-> Its a very important file
    its lock the version and keeps it.
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

devDepencies  -- dependencies for developement purpose, its not present in production

dependencies -- Its present globally(development + production)

16. what does babel do?
-> The main purpose of Babel is to make your code readable by older browsers.
    Babel transforms your modern JavaScript code into the older version, and then adds polyfills, a piece of code that implements features missing in the browser but needed by your app.


17. How create-react-app works?

18. diff btw npm and npx?
-> npm is used to download the javascript library and npx is use to execute the javascript package

19. Command that we ran during creating a react application?
->1. npm init
	Ask certain questions and create package.json file
   2. npm install  -D parcel
	After running this command the, we get package.lock json file.
	As any command that install package will create a package.lock.json file for storing 	data of that package.
	Here  "-D" means that this package is used for development purpose.

20. Why we need "npm" in our project?
-> Because npm manages packages, and we need packages for our project to run.
     Our react app is powered by a lots of packages eg;- to run, for minification, etc, for these       we need helper packages, which we get from npm.

21. npx means "execute using npm"

22. Now, we do start project :- npx parcel index.html
	As index.html is the starting point in our application.
	parcel craete a build and deploy in local server

23. Never touch node-modules and package.lock.json

24. what is type in script tag?

25. When we save changes in file, then automatically the server reloads and show the changes?
--> This functionality is called live server, but not all live server have this function.
	Parcel is doing this live server thing. Its called as Hot Module Reload (HMR).
	Parcel uses "file watcher algorithms" for this functionality, its written in C++

26. Parcel creates .parcel-cache file for its use.

27. for production build:- npx parcel build index.html

	It create a minified build for production and stores in .dist folder
	Here, we have to remove "  "main": "App.js", " from package.json as we have 		given the entry point of app in command

28. what parcel is doing?
-> HMR - Hot Module Replacement
Created a server
File Watcher Algorithms - C++
Bundling
Minify
Cleaning our code
manages dev and prod build
super fast build algorithms
Image Optimization
Caching while development :- when build is made again again then it take less time every time bcoz of cahing in ".parcel-cache" folder
compression
Compatible  with older version of browser
HTTPS on dev
manages the port number
Consistent hashing algorithms for caching
Zero config

Note:- IMAGE are heavy to load on prod
-> Bundler also uses node_modules

29. Production build takes more time than development build, as its more minified
30. ".dist" stores the minified files. Search about it.?
	PARCEL will create the minified file for js, css and keep it in .dist folder

31. We should put .parcel-cahe in git ignore?why? what things to put in git-ignore?
-> Anything that is auto-generated in server will be put in git ignore. 

32. why is React fast? 
-> Bcoz of a lot of things like, virtual DOM, Bundlers like parcel etc

33.USE WHILE INTERVIEW:
- Transitive Dependencies
we have package manager that handles and take care of transitive dependencies.

One dependency depends on another dependency, that dependency is also dependent on another dependency, so these dependencies are called Transitive Dependencies

32. React	along with parcel uses different dependencies, and those dependencied may also use some other dependency , this is called as dependency tree.

33. with the help of "browserlist" dependency we can target the different version of the browser, we can target the country as well :-

https://browserslist.dev/?q=bGFzdCAyIHZlcnNpb25z

34. Differ btw map and forEach?
-> 1. The map() method returns a new array, whereas the forEach() method does not return a new array.
   2. The map() method is used to transform the elements of an array, whereas the forEach() method is used to loop through the elements of an array.
   3. map has item, index, array in parameter, where array is the whole array

   <!--
    eg:- 
   function circleArea(radius) {
            return Math.floor(Math.PI * radius * radius);
        }
        let areas = circles.map(circleArea);
        console.log(areas); 
        -->

35. what are linter in js?

36. what are interceptor in axios?

















































