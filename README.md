# Angular4Carousel

Configurable angular carousel

##Demo

http://angular4-carousel.bitballoon.com/

## Getting started

`npm i --save-dev angular4-carousel`

Add following lines into your

_module:_

`import { CarouselModule } from 'angular4-carousel';`

add carousel in your module imports section<br/>
`imports: [CarouselModule]`

<br/>
_component template:_

`<carousel [sources]="imageSources" [config]="config"></carousel>`

<br/>
_component ts:_
 
```
import { ICarouselConfig, AnimationConfig } from 'angular4-carousel';
```

and add sources and config to component class
```
public imageSources: string[] = [
     'path to img1',
     'path to img2',
     'path to img3'
  ];
  
  public config: ICarouselConfig = {
     verifyBeforeLoad: true,
     log: false,
     animation: true,
     animationType: AnimationConfig.APPEAR,
     autoplay: true,
     autoplayDelay: 2000
  };
```
  
## Config

_verifyBeforeLoad_ <br/>
values: false, true <br/>
If true, each image will render to view if and when load.
If false, all images render as soon as carousel init.

_log_: <br/>
values: false, true <br/>
Log to console on image load success or error

_animation:_ <br/>
values: false, true <br/>


_animationType_: <br/>
value: AnimationConfig.APPEAR, AnimationConfig.SLIDE_OVERLAP, AnimationConfig.SLIDE

_autoplay:_<br/>
values: false, true

_autoplayDelay:_ <br/>
values: [number]

## API

You can catch event on image loaded <br/>
Add following lines into your component ts file:

Import:
`
import { CarouselService } from 'angular4-carousel';
`

in constructor:

`
constructor (private x: CarouselService) {}
`

and use:<br/>
```
this.x.onImageLoad().subscribe(
      (src) => console.log(src + ' - loaded'),
      (src) => console.log(src + ' - error'),
      () => console.log('all imgs loaded')
    )
```

