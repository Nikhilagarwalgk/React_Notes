@ Early Hints (HTTP 103) in Networking?

-> Early Hints is an HTTP status code (103) that allows the server to send preliminary headers before the final response, enabling browsers to preload resources earlier. It gives hint for preload, prefetch, preconnect, ddns-prefetch.

<img width="893" height="227" alt="image" src="https://github.com/user-attachments/assets/9a99a016-5d12-4201-83fd-4be8c96cf722" />

<img width="860" height="370" alt="image" src="https://github.com/user-attachments/assets/12f71de8-82f4-4640-966f-8d2b978181d2" />

<img width="878" height="246" alt="image" src="https://github.com/user-attachments/assets/9037cc20-1e28-4269-9189-e9bf2d09c9a6" />

<img width="853" height="358" alt="image" src="https://github.com/user-attachments/assets/d08fe618-763c-4765-8eea-f47c14e46533" />

<img width="874" height="371" alt="image" src="https://github.com/user-attachments/assets/732aece9-84b6-4e22-a239-cde51833692b" />

<img width="862" height="459" alt="image" src="https://github.com/user-attachments/assets/b695aef6-2731-4766-ad50-da58304a6fee" />

<img width="838" height="325" alt="image" src="https://github.com/user-attachments/assets/57bc82b5-7fdf-4a8d-aeff-bec4adce2ecf" />


@ A browser can handle 6-7 parallel request at a time.

@Brotli & Gzip - Compression Algorithms? 
--> Brotli and Gzip are compression algorithms used to reduce the size of files (HTML, CSS, JS, JSON) sent over the network, making websites load faster.

<img width="865" height="227" alt="image" src="https://github.com/user-attachments/assets/f353e033-3024-4d31-b406-bfa6c4f8e89d" />

1. Gzip
Gzip is the older, widely-supported compression algorithm (since 1992).
eg. Content-Encoding: gzip

2. Brotli
Brotli is a newer compression algorithm by Google (2015), offering better compression ratios.

eg. Content-Encoding: br

<img width="840" height="241" alt="image" src="https://github.com/user-attachments/assets/84832675-2af8-43d8-a2dc-f242ceb7932c" />

<img width="851" height="435" alt="image" src="https://github.com/user-attachments/assets/3ff0193d-f891-4fff-91ea-9e86b62db332" />


@ Caching:-
-> Cache policy (cache-control, expire etag, last-modifier). Browser cache memory is a storage area where your web browser saves copies of files from websites you visit. Its main purpose is to make websites load faster and reduce data usage.

Typical cached items include:- HTML pages, Images (logos, photos), CSS stylesheets, JavaScript files, Fonts, Videos or thumbnails.

These are saved so that the browser doesn’t have to download them again on your next visit.
 As you visit a website.

1. The browser downloads needed files and stores them in cache.

2. The next time you open the same site, the browser checks:

3. If cached files are still valid (based on expiry rules set by the website).

4. If valid, it loads them from your device instead of the internet → much faster.
   <img width="688" height="229" alt="image" src="https://github.com/user-attachments/assets/e33ee160-73c1-4564-8814-80d8ddd23562" />
   <img width="528" height="227" alt="image" src="https://github.com/user-attachments/assets/9dc3de02-0542-4a3b-92b6-b302792d978e" />
   <img width="537" height="288" alt="image" src="https://github.com/user-attachments/assets/96b2e897-6fee-4c69-80f8-de29b2d8e383" />
    <img width="542" height="170" alt="image" src="https://github.com/user-attachments/assets/60ccdbb6-cbb6-4514-9b23-d33ea0e3091f" />
Cache Storage is a browser API that stores request–response pairs to improve performance and support offline functionality

  <img width="870" height="332" alt="image" src="https://github.com/user-attachments/assets/31aa0d18-d4cb-45d4-af1d-5f22c22ccb9a" />


@ Once we call a request, we have data. But if again we need the same data we call network then it will give the data from the cache.
--> Yes, the browser cache the response data and if again call that API or website it first checks the cache data. If its there then its uses it else call the API. There are ways to control cache from frontend as
* fetch(url, { cache: "no-store" }); // Don't store cache
* fetch(url, { cache: "default" }); // use cache
* fetch(url, { cache: "no-cache" }); // Validate before use
  <img width="906" height="388" alt="image" src="https://github.com/user-attachments/assets/8c11d7ea-0299-4c70-b270-cfb577fe1f7f" />

Mostly the change is from backend in server header, if we want to change something intentionally then we can use cache code for that.

@ What is service worker?
--> A Service Worker is a special type of JavaScript file that runs in the browser separately from a web page. It acts as a programmable network proxy between the web page and the internet, giving websites capabilities like offline access, background syncing, and push notifications.

<img width="827" height="297" alt="image" src="https://github.com/user-attachments/assets/44bb9914-807c-449c-b50f-11ee063088e5" />


Think of it as a background worker for your website.

@ Frontend Question:- Select the grid box randomly and at last they should be deselected automatcally in backward sequence in which they were selected.

@ How JSX is excuted?
--> React uses tools like Babel to transform JSX into regular JavaScript.
In a React project, Babel is not included automatically with Webpack. It is usually installed as a separate library, even if you are using Webpack for bundling. Sometime we don't babel in dev dependencies then its integrated with webpack in webpack.config.js  .

@ How CSS is exucuted, both inline and css file?
--> Normal css file is directly loaded from bundle and loaded, parsed then coverted om CSSOM etc.
<img width="675" height="467" alt="image" src="https://github.com/user-attachments/assets/f874c07a-7226-4285-ab20-335dac242a59" />

When it comes to in-line CSS then React comes into picture,
<img width="824" height="505" alt="image" src="https://github.com/user-attachments/assets/1ce4b6a5-35d5-4e0d-93e8-a49bfd9778ee" />
<img width="729" height="342" alt="image" src="https://github.com/user-attachments/assets/89552273-4a1f-4254-952d-25ee36d31d77" />


@ what is CSS, SCSS, LESS etc ?
@ what is FOUT, FOIT ?
