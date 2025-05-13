# React_Notes

# None of your business

1. Revise prevoius lesson
2. What are bundlers- vite, parcel, webpack-->?
   => A bundler is a tool that puts together all your JavaScript code and its dependencies and throws a new JavaScript output file with everything merged, ready for the web, commonly known as the bundle file.

- /dist will be the folder created after the bundle process and will contain all the bundled files.
    Common Files in /dist Folder (Production Build)
    Here’s what you might find in a /dist folder:

   1. index.html ->	The main HTML file served to the browser. It includes links to the JavaScript and CSS bundles.
   2. main.[hash].js ->	Minified and bundled JavaScript file(s), often with hash in filename for cache busting.
   3. main.[hash].css ->	Bundled and minified CSS file(s), also hashed for cache busting.
   4. assets/ or static/ ->	Folder with images, fonts, or other static assets. Sometimes broken into js/, css/, media/, etc.
   5. favicon.ico ->	Website favicon (if added).
   6. manifest.json ->	Metadata for Progressive Web App (optional).
   7. robots.txt ->	Instructions for search engine crawlers (optional).
   
- /src is the folder containing the entry point from which the bundler will start the bundle process.

- /styles is the folder containing the original styles file, before the bundle.

- index.html is the file containing what we'll see in the browser.

- package.json is the file where all the dependencies, scripts and some configurations are stored.

- .config.js is the file where all the config for the bundler is defined. This file is optional for every bundler in this list, but highly recommended. \* will be replaced accordingly by the name of the bundler.

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

      "^" ->	Compatible with the current version	-> ^1.2.3. Supoorts >=1.2.3 but <2.0.0.
      Keeps major version pinned, but updates minor and patch versions.

      "~" ->	Approximately equivalent (patch updates only) -> ~1.2.3. Supports	>=1.2.3  but not <1.3.0
      Keeps major and minor version fixed.

      eg:- 18.1.6 where 
            18 is major version
            1 is minor version
            6 is patch


11. package without these sign means, they want to use this specific version?
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
    ![image](https://github.com/user-attachments/assets/0cce0e38-781d-4f7b-8871-3ae32992a858)


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
2. What are bundlers- vite, parcel, webpack?
   -> React uses different bundlers like, webpack, browserfy, rollup and Parcel.
   Bundler does a lot of things to optimize the react code 1. Code Splitting 2. React.lazy

   A bundler is a tool that puts together all your JavaScript code and its dependencies and throws a new JavaScript output file with everything merged, ready for the web, commonly known as the bundle file.

- These bundlers can work with other types of files as well apart from JavaScript, but they need a little help to perform their bundles. We'll talk about this more in depth in each of the examples below.

- /dist will be the folder created after the bundle process and will contain all the bundled files. The bundled file for the styles is optional because we can choose either to inject the styles directly in the HTML or generate a new transpiled file containing the styles.

- /src is the folder containing the entry point from which the bundler will start the bundle process.

- /styles is the folder containing the original styles file, before the bundle.

- index.html is the file containing what we'll see in the browser.

- package.json is the file where all the dependencies, scripts and some configurations are stored.

- .config.js is the file where all the config for the bundler is defined. This file is optional for every bundler in this list, but highly recommended. \* will be replaced accordingly by the name of the bundler.

# Feature of Parcel during development:-

1. parcel uses Hot reloading using the Hot Module Replacement (HMR).HMR improves the development experience by updating modules in the browser at runtime without needing a whole page refresh. This means that application state can be retained as you change small things in your code.

In simple, it automatically loads application when we save the changes in VS code.

- Extra :- If you’re not using a framework, you can opt into HMR using the module.hot API. This will prevent the page from being reloaded, and instead apply the update in-place. module.hot is only available in development, so you'll need to check that it exists before using it.

2. Lazy mode
3. Caching
4. HTTPS - We can use https in development server using command, "parcel src/index.html --https"
5. API proxy
6. File watcher - Using this watcher Parcel watches every file in your project root (including all node_modules). Based on events and metadata from these files, Parcel determines which files need to be rebuilt. (Written in C++)
7. Auto install - When you use a language or plugin that isn’t included by default, Parcel will automatically install the necessary dependencies into your project for you. For example, if you include a .sass file, Parcel will install the @parcel/transformer-sass plugin. When this happens, you'll see a message in the terminal, and the new dependency will be added to the devDependencies in your package.json.

# Code Splitting

Parcel supports zero configuration code splitting out of the box. This allows you to split your application code into separate bundles which can be loaded on demand, resulting in smaller initial bundle sizes and faster load times.

1. Tree shaking :- When Parcel can determine which exports of a dynamically imported module you use, it will tree shake the unused exports from that module. This works with static property accesses or destructuring, with either await or Promise .then syntax.

2. Shared bundles:- When multiple parts of your application depend on the same common modules, they are automatically deduplicated into a separate bundle. This allows commonly used dependencies to be loaded in parallel with your application code and cached separately by the browser.

<------------------------------------------------------------------------------------------------------------> 3. find the difference btw them?
4.what is npm and yarn?
5.npm doesnt statnd for node package manager(see doc)?

6. how 'npm inti' works?
   -> Its created a package.json file for the project.

Try:- npm init -y, what it does?

7. Useing 'parcel' or 'webpack'?
   -> Advanatge of using Webpack:-
1. It helps to use different javascript files without having tension that will load first.
1. It makes code shorter.
1. It helps in converting many files other than javascript into modules.
1. It compiles different javascript module.

- having all js bundled together into one file - which gives us a better performance on production deployment.
- simpler imports of npm dependencies. The bundler-free approach works but feels a bit hacky and it's more hassle to maintain.
- build-in code optimization applied automatically by webpack
- it opens doors for many futures improvements - transpiling code so we can use new language features while supporting older browsers; including styles directly from the app or moving our code base to typescript.

8. if we only want to use parcel during development not production?
   ->npm install parcel (production, when we want it globally)
   npm install -D parcel (developement, here D is for dev dependencies)
   npm install --save-dev parcel (development, same)

dev dependencies are those that our project needs for development, eg:- parcel.

9.  learn about ^(caret) and ~(tilde) in packages ?
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

devDepencies -- dependencies for developement purpose, its not present in production

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
20. npm install -D parcel
    After running this command the, we get package.lock.json file.
    As any command that install package will create a package.lock.json file for storing data of that package.
    Here "-D" means that this package is used for development purpose.

21. Why we need "npm" in our project?
    -> Because npm manages packages, and we need packages for our project to run.
    Our react app is powered by a lots of packages eg;- to run, for minification, etc, for these we need helper packages, which we get from npm.

22. npx means "execute using npm"

23. Now, we do start project :- npx parcel index.html
    As index.html is the starting point in our application.
    parcel craete a build and deploy in local server

24. Never touch node-modules and package.lock.json

25. what is type in script tag?

26. When we save changes in file, then automatically the server reloads and show the changes?
    --> This functionality is called live server, but not all live server have this function.
    Parcel is doing this live server thing. Its called as Hot Module Reload (HMR).
    Parcel uses "file watcher algorithms" for this functionality, its written in C++

27. Parcel creates .parcel-cache file for its use.

28. for production build:- npx parcel build index.html

    It create a minified build for production and stores in .dist folder
    Here, we have to remove " "main": "App.js", " from package.json as we have given the entry point of app in command

29. what parcel is doing?
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
    Compatible with older version of browser
    HTTPS on dev
    manages the port number
    Consistent hashing algorithms for caching
    Zero config

Note:- IMAGE are heavy to load on prod
-> Bundler also uses node_modules

29. Production build takes more time than development build, as its more minified
30. ".dist" stores the minified files. Search about it.?
    PARCEL will create the minified file for js, css and keep it in .dist folder

31. We should put .parcel-cache in git ignore?why? what things to put in git-ignore?
    -> Anything that is auto-generated in server will be put in git ignore.

32. why is React fast?
    -> Bcoz of a lot of things like, virtual DOM, Bundlers like parcel etc

33.USE WHILE INTERVIEW:

- Transitive Dependencies
  we have package manager that handles and take care of transitive dependencies.

One dependency depends on another dependency, that dependency is also dependent on another dependency, so these dependencies are called Transitive Dependencies

32. React along with parcel uses different dependencies, and those dependencied may also use some other dependency , this is called as dependency tree.

33. with the help of "browserlist" dependency we can target the different version of the browser, we can target the country as well :-

https://browserslist.dev/?q=bGFzdCAyIHZlcnNpb25z

34. Differ btw map and forEach?
    -> 1. The map() method returns a new array, whereas the forEach() method does not return a new array.

- The map() method is used to transform the elements of an array, whereas the forEach() method is used to loop through the elements of an array.
- map has item, index, array in parameter, where array is the whole array

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

## Laying the foundation - FOURTH DAY

git init - create a file as .git-ignore

Super power of parcel:-
Hot Module Replacement
minification
compression
build caching
cleaing - console
Tree Shaking :- Removing unwanted code (Heavy word use in interview, but first read about it)
etc read it.

READ About WEBPACK. (Add it in resume)

1. If we want to start the project then,
   npx parcel index.html

To create new command:-
in package.json in script add:-
"start" : "parcel index.html"
then, npx start

To create build:-
npx parcel build index.html

To create new command:-
in package.json in script add:-
"build" : "parcel build index.html"
then, npx build

2. npx - Only execute a package
   npm - Download a package
   So, if want to execute a pakage or a script from package.json through npm then,
   npm run \_\_\_ is used.
   so,

Now, we use --> npm run build === npx build
npm run start === npm start

3. NOTE:- Parcel does not remove console.log, we have to configure it to do.
   Install npm :- babel plugin transform remove console

4. sometime we have key warning, for the sibling data then give key attribute in render
<h1 key="h1"> name<h1>
<h1 key="h2"> name<h1>

"key" are unique for every data.

5. Read about "Reconciliation" from react doc.
   ->The concept of virtual DOM and real DOM, while updating the UI is called as Reconciliation.

- Diffing Algoriythms:-When diffing two trees, React first compares the two root elements. The behavior is different depending on the types of the root elements.
  For more details:- https://reactjs.org/docs/reconciliation.html

6. what is re-render or render?
   ->updating something in DOM

7. React.createElement gives us an Object, and that object is converted into html(DOM)

8. Is JSX == "html inside Javascript" => No
   eg:- (JSX Expression OR React Element)

const heading = <h1 id="title" key="h2">Namaste react</h1>

@what is above ? what is JSX?
-> Its in js file, so its html like syntax not html, its a fancy way of writting html inside javascript

JSX is a html like syntax but its not html

## what is JSX?

-> eg :- const element = <h1>Hello, world!</h1>;
JSX produces React “elements”. We will explore rendering them to the DOM.

## Why JSX?

1. Embedding Expressions in JSX -> In the example below, we declare a variable called name and then use it inside JSX by wrapping it in curly braces.In the example below, we declare a variable called name and then use it inside JSX by wrapping it in curly braces.

2. JSX is an Expression Too -> After compilation, JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects.

This means that you can use JSX inside of if statements and for loops, assign it to variables, accept it as arguments, and return it from functions:eg:-

function getGreeting(user) {
if (user) {
return <h1>Hello, {formatName(user)}!</h1>;
}
return <h1>Hello, Stranger.</h1>;
}

3. Specifying Attributes with JSX -> You may use quotes to specify string literals as attributes.
   eg :- const element = <a href="https://www.reactjs.org"> link </a>;

4. Specifying Children with JSX -> If a tag is empty, you may close it immediately with />, like XML.

const element = <img src={user.avatarUrl} />;
JSX tags may contain children:

const element = (

  <div>
    <h1>Hello!</h1>
    <h2>Good to see you here.</h2>
  </div>
);

# Most Important Usage

5. JSX Prevents Injection Attacks -> By default, React DOM escapes any values embedded in JSX before rendering them. Thus it ensures that you can never inject anything that’s not explicitly written in your application. Everything is converted to a string before being rendered. This helps prevent XSS (cross-site-scripting) attacks. As all the JS attack code is converted into normal string, so the attack doesn't works.

6. JSX Represents Objects -> Babel compiles JSX down to React.createElement() calls.

# <------------------------------------------------------------------------------------------------------------>

9. React keep track with "key", html with "id" they are diiferenet.

10. what is a difference between html and JSX?

11. Read about babel, its a library in itself.
    -> Babel is a JavaScript compiler, that converts the JSX into the React.Element

12. JSX is understand by babel in react application.

13. how JSX works?
    -> JSX => React.createElement => Object => HTML(DOM)

14. play with Babel compiler in its website, write JSX there and get to know how it works

15. Advantage of JSX:-
    Readability
    syntax
    maintainance
    Read Above

16. There one more package.lock.json inside node_modules, to maintain version of files or libraries in node_module
    Here, we find babel library

17. Name of Component starts with capital letter, why?
    -> Bcoz its a good practice, its not mandatory

18. Functional Component is a normal function. It just returning some jsx

19. Diiferent ways to return in functional component or arrow function?
    -> 1.
    const HeaderComponent = () => {
    return(
    <div>
    <h1> name</h1>
    </div>
    )
    }

20. const HeaderComponent2 = () => {
    return <div><h1> name</h1></div>
    }

21. const HeaderComponent = () => (
    <div>
    <h1> name</h1>
    </div>
    )

22. const HeaderComponent = function () {
    return(
    <div>
    <h1> name</h1>
    </div>
    )
    }

23. Call a component inside another component:-
    -> const Title = () => (
    <div>
    <h1> name</h1>
    </div>
    )

const head= (

<div>
<h1> name</h1>
</div>
)

const HeaderComponent = () => {
return(

<div>
<Title /> OR {Title()}
<h1> name</h1>
{head}
</div>
)
}

bcz functional component are also a function at the end of the day.

21. We can write any piece of javascript code in JSX using parenthesis {}.
    console.log also inside {}.

22. If we write any data that come from an api that has XXS (hacked ) in JSX eg:- inside {}, then it make sure that its secure.
    first JSX "sanitize" the data first and then it send to browser. It protect from XXS- cross-site scripting
    (Read about it)

23. Using one component inside another component is called componenet composition.

24. Parcel uses Babel, babel converts the JSX into HTML in DOM

25. .babelrc file -> has configuration for the babel

<!-- TCS -->

coding on number

1. All hooks
2. Box model, css selector
3. what are fragment
4. Css - grid box, html- meta tag
5. What is Higher Order Component? Have you used any in your project?
   How do you Handle API calls on your React App?
   How do you chain multiple API calls that is depending on the previous request?
   How will you optimize a React Application?
   What is a Pure Component and how will you do the same on functional components?
   Explain controlled and uncontrolled components?
   Redux Questions on Actions, reducers, and state
   How to avoid mutating an array when performing an operation
   Explain this keyword with arrow function and normal function
   What is event bubbling?
   What ES6 features you have used?
   What is the difference between map, filter, and foreach?
   Deep copy vs Shallow copy

# DO the assignment of Fourth Video

1. DO - npx create react app
   -> See whats their in folder and understand them

2. Command need to initialise npm -> npm init

# Talk is chep, show me the code! - Five

1. JOIN THE discord community

2. JSX is converted into ReactElement, by Babel
3. Functional Component are just a normal function
4. variabel starting with small and component name with capital letter
5. Component is JSX can be call as a normal function as well,
<Title /> - self closing tag
or {Title()} or <Title></Title>

6. Any calculation can be done in JSX inside {}
7. How to write commet in jSX?
   -> Inside JSX
   {
   <!-- Here comment can be written -->
   }
8. JSx is not manadatory for React

# Install good notes application in laptop

<!-- TODO :  -->

1.  why we use axios, when we have fetch?
2.  why we have semantic, cant we write our header in div tag, why header tag is there?
    -> Semantics makes the code better for the code, as the tech ot non-tech person can understand the data with the semantics name.
    It help in improving the SEO(Search Engine Optimization), as the web bot can understand the semantic elements.
    This refers to the way in which search engines such as Google interpret the content of your site and it can affect where your site will appear in search results. This means that neglecting semantic HTML could have a negative effect on how many users will find and interact with the site.

- Code readability and maintainability

\*The semantics of an entity describes what its purpose is. By using semantic HTML elements we are able to provide meaning to the structure of our code. eg:- header, footer, li, ui, etc

NOTE:- Always remember that your code will not work, so error handling should be done every where.

*If adding image, then if image is not shown - add alternate text
*If api calling,and Api is failed - do error handling
\*If making component, then component is not working so add error boundaries

Question on API call:-

1. How data is transfered in JSON? what is JSON?
2. what is request waterfall?

<--------------------------------------------------------->

3. why JSX have only one parent element?
   -> This is so, Bcoz a component is a function at the end of the day, as function return data or value , component also return JSX elements.
   Now, according to basic of a function, a function cannot return multiple value
   eg:- function returnSelf(a, b) {
   return (
   a
   b
   )
   }
   This is invalid syntax, So adjacent elements are not allowed. We need to have a single value to be returned as:-
   function square(a) {
   return (
   a \* a;
   )
   }
   So, The JSX must also have a single returned value and to do this, we should enclose it in a parent element.

4. So , if we give a parent div then, one more div is added. So, to avoid this we use React.Fragment.
   React.Fragment is a component of react, that can be used as a parent element but it doesnt add any extra div in elemet,we can Inspect and see.
   It can be called as an
   <React.Fragment>
   .......
   <React.Fragment>
   OR
   <>
   .......
   </>
5. In React, we give styling in object as:-
   style={{color: "red}}

or

styleObj={
color: "red
}
style={styleObj}

@why return statement has ()- common bracket

6. \*\* USE IN INTERVIEW
   BIG company uses - Congif Driven UI
   where data comes from backend, and UI shows it.

7. Optional Chaining :-
   It checks if the value is undefined, if the value is undefined then it will not give error in react app.(App fatega nhi).
   Optional Chaining is incredibly useful, and widely supported (excluding Internet Explorer). It can be used with pretty much any combination of property, array or function, depending on return types. For example:

obj?.property
obj?.[property]
obj[index]?.property
obj?.(args)
func(args)?.property

eg :- data?.name

- Nullish Coalescing:- In Javascript, the nullish coalescing operator, or ?? operator is used to return the right hand side whenever the left hand side is null or undefined. To understand a little bit better, let’s look at a few examples:
  // Is set to 0
  let x = 0 ?? "hello";

// Is set to goodbye
let y = undefined ?? "goodbye";

// Is set to hello
let z = null ?? "hello";

// Is set to false
let a = false ?? "goodbye";

\*\* GOOD TO KNOW:- It's good to know that by default, if a function has no return, it returns undefined

8. props - properties in react

9 what are argument and parament?
-> function Name(param1, param2){
}
Data function receive is parameter

Name("Nik","123");
Data passed while calling a function is function argument.

So, we pass arguments and receives parameter.

10. When we call any component , then its same as calling a function,
    <restaurant data={res[0]) /> === {restaurant(res[0])}

A component is a function at the end of the day.

11. props can be used in different ways:-
1. const Restaurant = ({props}) = {
   props.restaurant?.name
   props.restaurant?.food
   props.restaurant?.start
   }

1. const Restaurant = ({ restaurant }) = {
   restaurant?.name
   restaurant?.food
   restaurant?.start
   }

1. const Restaurant = ({props}) = {
   const {name, food, star} = restaurant.data
   name
   food
   start
   }

1. const Restaurant = ({
   name,
   food,
   star
   }) = {
   Use it as:-
   name
   food
   start
   }
   For this we also have to pass data in this way:-

<Restaurant name={reastaurant?.data.name} food={restaurant.?.data.food} star={restaurant?.data.star} />
OR
<Restaurant {...restaurant?.data} />                  {Amazing}

12. Virtual DOM is the representation of the real DOM,
    virtual DOM is needed for Reconcialation.
    Reconcialatio is a concept of react- read official doc,
    So, basecally diff alogorithms updates it.

\*When any node is updated in the DOM, their child nodes are also updated. Their parent node is not updated

\*Suppose a node has 3 child nodes, if i add one more node in react, then react will have problem in identifying which node has added so it will update all the sibling nodes but the added node should be of same type
eg
There are 3 div, one more div is added, then react will have problem in identifying the new div, so it will update all the div in that row
BUT
There are 3 div, one more image tag is added, then react can identifying the new image, so it will update image tag in that row. React can identify different types of tags, like div, img, boby etc

So, to avoid that extra rendering in react, we give Key to the div, with the help of key react understands, which div is recently added and which divs where already their, and it updates only the new div.

\*diff algorithms is similsr to git diff

\*Reconcialiation uses diff alogothrims and find the difference btw the tree, and update only that portion of app which diff algorithms founds it

13. React Fiber - Read about it- in homework thier is link to read.
    \*Its a new Reconcialaton engine in react 16, and this is responsible for diff algorithms

14. Never use index as a key? why? - Read officila doc
    Using Unique key is best practice
    Index can be used, if there are no unique key

Index are not a good practice to use as a key, suppose we used index as key:-
eg:- <ul>

  <li key=1>Milk</li>
  <li key=2>Eggs</li>
  <li key=3>Bread</li>
</ul>

If we add an item to the end of the list, React no longer needs to re-render the first 3 list items which are same. It will just add a new list item at the end:-
eg:- <ul>

  <li key=1>Milk</li>
  <li key=2>Eggs</li>
  <li key=3>Bread</li>
  <li key=4>Butter</li>
</ul>

But suppose we add the new item at the beginning of the list.Now, the key of remaining list items also changes, which makes React re-render all the elements again, instead of just adding a new item at the end.
This can be avoided if we use some unique id as a key rather than index.
Let's again consider the same previous example but this time by using a unique id as key.

<ul>
  <li key="12abc">Milk</li>
  <li key="23bcd">Eggs</li>
  <li key="34cde">Bread</li>
</ul>
Now even if we add element to the beginning or the end, we won't face an issue since keys are different.

** Always prefer using a unique id as value for the key attribute in a list and avoid using index.
**Using index might result in performance issues and data binding issues in case reordering in the form of sorting, filtering might happen.

- no key < index < unique key
  no key se acha h index, or index se acha h unique key

  ## Interview Question:-

  Question Asked in interview:-

1. Implement promise, closure, asyn await
2. Print 1 to 6
3. Make a clock, css question
4. How will you implement, trending page of twitter- So, generally want to know how u will do API call, how many API are needed, when willl the API will be called.what will happen if certain API fails
   Trending page of youtube.
5. Knowledge about browser, How does a browser works?
   Know about browser?
6. Back ground me html kaise chalata h
7. Improve performance, cacheing,

## Lets build Our Store

1. We use context API to avoid props drilling
2. For small application, we dont use redux
3. Redux is used for data management
4. Flow of redux

Click on Add ---> dispatch Actipn will call a function ---> This will modify our cart(slice of the store)

Here, the function is known as Reducer.

Whwn we click on a button the, it will dispatch an action, whitch will call a Reducer function, and this function will update the slice of the store.

Again,
onClick a button
dispatch an Action
It calls the Reducer Function
Reducer function updates the Slice of a redux store

To fetch data from store we use Selector.
Selector - selecting a portion of the store
useSelector is a hook, hooks are a function

when we update store, then it will automatically upadate the UI.

5. npm i @reduxjs/toolkit
   npm i react-redux

@why two library?
-> first(@reduxjs/toolkit) is the core library , second(react-redux) is the bridge between react and redux
RTK = redux toolkit

6.reducer function don't return (1:30 hrs)

7. subscribe to store means in sync with store, mostly the component useing store are subscribe my store.

8. Flow of redux while writing:-
   Create Store - configure store() - RTK

Provider my store to app - <Provider store = {store} /> - import from react-redux

Create a slice - createSLice({ - redux/toolkit or RTK
name: "",
initialState:{
}
reducer:{
addItem: (state, action)=>{state=action.payload}
}
})
export default userSLice.reducer;

Put that Slice in Store
-{
reducer:{
user: UserSlice,
}
}

9. Redux is very big library and has a lot of interesting things to explore.GO and find it...

10. Only subscribe to speecific portion of the store, eg : cartSlice, foodSlice. etc. not the whole store.(It will optimise the app)

eg:-
const cartItem = useSelector((store) => store.cart.item) ----(RIGHT)

const store = useSelector((store) => store)) ------(WRONG)

11. Work with redux dev tookkit... its amazing
