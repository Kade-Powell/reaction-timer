# reaction-timer

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### cheat code

```
function checkForBlock () {
    if(document.getElementsByClassName('block')[0]){
        document.getElementsByClassName('block')[0].click()
    }else{
        setTimeout(()=>{
            checkForBlock()
        })
    }
}
checkForBlock()
```
