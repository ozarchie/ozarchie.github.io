# Nano Hydroponics

## Overview
This ESP32-nano project builds a fully automated nano-hydroponics system utilizing online limit controls and as much recycling as possible.  

Software was developed using arduino-esp32 and is fully interrupt driven using a multi-cpu multi-task design methodology.

The system software is used to sense -:  
 
1. the air temperature and humity
2. the water temperature and level
3. the water EC/PPM level
4. the water pH level
5. a lux meter

The system software is used to control -:  
 
1. the automated flow of nutirent enriched water
2. the hothouse air evacuation pump, or air heater
3. the water top-up valves
4. the water pH
5. the light level 

The system is built by recycling as much computer waste as possible. Th EC sensor is built from a surplus AC plug. The nutrient and pH pumps are re-claimed from an inkjet printer.  

The complete system is controlled online using Thingspeak, where the water, temperature, humidity, EC/PPM, pH and lux limits are set.  

A secondary project removes all the wiring by using ESP8266 to provide bluetooth wireless monitoring and control of the sensors pumps lighting and fans.

___

## Hardware
### Temperature
There are two temperature sensors in the project. The air temeprature is sensed using a DHT22. This controls the humidity level. The water temerature is  sensed using a DS18B20. It is used in conjunction with the EC/PPM sensor to compensate the EC/PPM levels.
### Humidity
The humidity is sensed using a DHT22 sensor. It is used in conjunction with the air temperature to control the humidity level.
### Water Level
The water level is sensed using a recycled water float and microswitch. It is used to control the nutrient water level.
### EC / PPM
The EC/PPM sensor is constructed from a used AC round prong electrical lead. A standard two prong soil moisture sensor can also be used. The sensing is temperature compensated, and modulated to reduce fouling and corrosion.
### Relays
Standard relay-based controls allow for multiple types of light, motor, pump and valve interfaces. In the prototype, recycled washing machine water valves and tap timers provided the water controls. A recycled peristaltic pump was used for nutrient control. A 12V automobile fan was used for humidity reduction. A 12V LED strip was used for lighting.  

The same interface could be used for SSR relays for AC powered fans, pumps and lights.

The interface also allows of-the-shelf bluetooth or wifi items to be used.
### Cabling
All cables are run using standard 3-pin 2.5mm stereo jacks.


___

## Software
All the software was designed using the Arduino ESP32 software development environment.  

Installation instructions and setup can be found here [arduino-esp32]  (https://github.com/espressif/arduino-esp32).

This document is maintained here [esp32-nano-hydro]  (https://github.com/ozarchie/ozarchie.github.io).
### Arduino
### Libraries
### Special Libraries
### Tasks
### IOT
___

## IOT
### Thingspeak
### Setup
### Limits
### Controls
___

#### h4 Heading
##### h5 Heading
###### h6 Heading


## Horizontal Rules

___

---

***


## Typographic replacements

Enable typographer option to see result.

(c) (C) (r) (R) (tm) (TM) (p) (P) +-

test.. test... test..... test?..... test!....

!!!!!! ???? ,,  -- ---

"Smartypants, double quotes" and 'single quotes'


## Emphasis

**This is bold text**

__This is bold text__

*This is italic text*

_This is italic text_

~~Strikethrough~~


## Blockquotes


> Blockquotes can also be nested...
>> ...by using additional greater-than signs right next to each other...
> > > ...or with spaces between arrows.


## Lists

Unordered

+ Create a list by starting a line with `+`, `-`, or `*`
+ Sub-lists are made by indenting 2 spaces:
  - Marker character change forces new list start:
    * Ac tristique libero volutpat at
    + Facilisis in pretium nisl aliquet
    - Nulla volutpat aliquam velit
+ Very easy!

Ordered

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa


1. You can use sequential numbers...
1. ...or keep all the numbers as `1.`

Start numbering with offset:

57. foo
1. bar


## Code

Inline `code`

Indented code

    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code


Block code "fences"

```
Sample text here...
```

Syntax highlighting

``` js
var foo = function (bar) {
  return bar++;
};

console.log(foo(5));
```

## Tables

| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |

Right aligned columns

| Option | Description |
| ------:| -----------:|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |


## Links

[link text](http://dev.nodeca.com)

[link with title](http://nodeca.github.io/pica/demo/ "title text!")

Autoconverted link https://github.com/nodeca/pica (enable linkify to see)


## Images

![Minion](https://octodex.github.com/images/minion.png)
![Stormtroopocat](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")

Like links, Images also have a footnote style syntax

![Alt text][id]

With a reference later in the document defining the URL location:

[id]: https://octodex.github.com/images/dojocat.jpg  "The Dojocat"


## Plugins

The killer feature of `markdown-it` is very effective support of
[syntax plugins](https://www.npmjs.org/browse/keyword/markdown-it-plugin).


### [Emojies](https://github.com/markdown-it/markdown-it-emoji)

> Classic markup: :wink: :crush: :cry: :tear: :laughing: :yum:
>
> Shortcuts (emoticons): :-) :-( 8-) ;)

see [how to change output](https://github.com/markdown-it/markdown-it-emoji#change-output) with twemoji.


### [Subscript](https://github.com/markdown-it/markdown-it-sub) / [Superscript](https://github.com/markdown-it/markdown-it-sup)

- 19^th^
- H~2~O


### [\<ins>](https://github.com/markdown-it/markdown-it-ins)

++Inserted text++


### [\<mark>](https://github.com/markdown-it/markdown-it-mark)

==Marked text==


### [Footnotes](https://github.com/markdown-it/markdown-it-footnote)

Footnote 1 link[^first].

Footnote 2 link[^second].

Inline footnote^[Text of inline footnote] definition.

Duplicated footnote reference[^second].

[^first]: Footnote **can have markup**

    and multiple paragraphs.

[^second]: Footnote text.


### [Definition lists](https://github.com/markdown-it/markdown-it-deflist)

Term 1

:   Definition 1
with lazy continuation.

Term 2 with *inline markup*

:   Definition 2

        { some code, part of Definition 2 }

    Third paragraph of definition 2.

_Compact style:_

Term 1
  ~ Definition 1

Term 2
  ~ Definition 2a
  ~ Definition 2b


### [Abbreviations](https://github.com/markdown-it/markdown-it-abbr)

This is HTML abbreviation example.

It converts "HTML", but keep intact partial entries like "xxxHTMLyyy" and so on.

*[HTML]: Hyper Text Markup Language

### [Custom containers](https://github.com/markdown-it/markdown-it-container)

::: warning
*here be dragons*
:::
