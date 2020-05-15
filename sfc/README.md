# 2020-05-14: Dynamische SVG

## Voraussetzungen

* node.js https://nodejs.org/de/
* Vue CLI https://cli.vuejs.org/guide/installation.html
* (optional) Vue-Devtools im Browser


## Input

Community-Logo von Manuel `cto_logo_02_mit_SchriftDinPro-01.svg`, 
geringfügig nachbearbeitet: `./input/Contao-Community-Bayern.svg`


## Vue CLI Create Project 

```
mkdir 2020-05-14 
cd 2020-05-14
vue create . 
```

oder 

```
vue create 2020-05-14
cd 2020-05-14
```

## Erster Start

```
npm run serve
```

## Weg mit dem nicht benötigten Demo-Inhalt

## SVG einbinden

* copy/paste 1:1 erzeugt "Warnings" 

```
Templates should only be responsible for mapping the state to the UI. 
Avoid placing tags with side-effects in your templates, such as <style>, as they will not be parsed.
```

* also `<style>` verschoben (innerhalb der Datei `HelloWorld.vue`)


## Und jetzt, wozu das Ganze?

* wir haben nun im SVG dynamisch änderbaren Text, den wir zunächst nur in der Datei `App.vue`
  ändern können. (Demo "hot reload")

  
## Textfeld hinzufügen

## Build

```
npm run build
```

## Ausblick: Inline SVG für "Bild speichern unter ..."

* Inline SVG
* vs. `<img src="foo.svg">`

```
<script>
    let svg = document.getElementById("svg");
    let serialized = new XMLSerializer().serializeToString(svg);
    // let dataurl = 'data:image/svg+xml;base64,' + btoa(serialized);
    let dataurl = 'data:image/svg+xml;utf8,' + serialized;
    let img = document.getElementById('img')
    img.src = dataurl;
    let bbox = svg.getBBox()
    img.width = parseInt(bbox.width, 10) + 2*parseInt(bbox.x, 10)
    img.height = parseInt(bbox.height, 10) + 2*parseInt(bbox.y, 10)
    // svg.parentNode.removeChild(svg);
</script>
```
