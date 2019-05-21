# svelte base PWA app

```bash
npm install
npm run dev
```

Navigate to [localhost:5000](http://localhost:5000). You should see your app running. Edit a component file in `src`, save it, and reload the page to see your changes.

## Deploying to the web

### With [now](https://zeit.co/now)

Install `now` if you haven't already:

```bash
npm install -g now
```

Then, from within your project folder:

```bash
now
```

As an alternative, use the [Now desktop client](https://zeit.co/download) and simply drag the unzipped project folder to the taskbar icon.

### With [surge](https://surge.sh/)

Install `surge` if you haven't already:

```bash
npm install -g surge
```

Then, from within your project folder:

```bash
npm run build
surge public
```
## creation steps

Started from   
https://svelte.dev/examples#hello-world

05/21/2019 8:17 AM  
Added lighthouse suggestions:  
01 - html tag: lang="en-US"  
02 - meta description tag  
![alt text](./src/assets/lighthouseScores/2019_0521_01.png "Lighthouse score")  

05/21/2019 11:54 AM  
Made it a PWA  
PWA Checklist:  
https://developers.google.com/web/progressive-web-apps/checklist  
How To Video:  
https://www.youtube.com/watch?v=dXuvT4oollQ  
![alt text](./src/assets/lighthouseScores/2019_0521_02.png "Lighthouse score")  
