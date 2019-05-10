# CAMERA TRANSITIONS

By [Pol Casaú](https://linkedin.com/in/pol-casaú-779045181/), student of the [Bachelor’s Degree in Video Games by UPC at CITM](https://www.citm.upc.edu/ing/estudis/graus-videojocs/). This content is generated for the second year’s subject Project 2, under the supervision of lecturer [Ricard Pillosu](https://www.linkedin.com/in/ricardpillosu/?originalSubdomain=es).

## TABLE OF CONTENTS

- CAMERA TRANSITIONS

- TYPES OF TRANSITIONS

- TIPS

- HOW DOES IT WORK?

- TODO'S

- WEBGRAPHY

## CAMERA TRANSITIONS
Camera transitions are a technique used in films or video editing to move from one scene to another one. They are also applied to video games, but before focusing on them, let's talk about transitions in general.

__When do we use camera transitions?__

If two scenes are happening at the same time and place, it is used a basic cut, with no transition, where the first shot is replaced by the next one.
If we want to give more emphasis to the change of scenes, for example to move forward or backward in time, or to switch to another point of view, we use the camera transitions to get that effect.

## TYPES OF TRANSITIONS
When we want to find information about camera transitions, we find out that most of the famous transitions we are used to see, appeared on TV before its application to video games, so you will see now the types of transitions classified into the ones that are seen on television and the ones that are exclusively on videogames.

### TELEVISION

- __Fade In / Out:__ The scene is turning gradually to a single color. Black and white are the most common ones; fading to black is used in dramatic or emotional scenes, or to introduce the credits at the end of a film, while fading to white is used to create a sense of hope or ambiguity.

![Fade to black](https://raw.githubusercontent.com/Bullseye14/Camera-Transitions/gh-pages/Images/FadeToBlack.gif)

_Fade to black example_

- __Dissolves:__ The dissolve overlaps two scenes. The first one gradually disappears while the scene is transitioning from one shot to the next one.

![Dissolve](https://raw.githubusercontent.com/Bullseye14/Camera-Transitions/gh-pages/Images/Dissolve.gif)

_Dissolve example_

- __Wipes:__ This happens when a shot travels from one side of the screen to the other, replacing the previous scene. It exists the _whip pan_, which is a sub cathegory of wipe, but it tends to be much faster. The whip pan is not always changing from one scene to another, but can be used to change the angle in the same shot.

![Wipe](https://raw.githubusercontent.com/Bullseye14/Camera-Transitions/gh-pages/Images/Wipe.gif) 

_Wipe example_

![Whip pan](https://raw.githubusercontent.com/Bullseye14/Camera-Transitions/gh-pages/Images/Whip%20pan.gif)

_Whip pan example_

- __Zoom:__ This type of transitions are used to give the sensation of increasing pace while switching between scenes.

![Zoom](https://raw.githubusercontent.com/Bullseye14/Camera-Transitions/gh-pages/Images/Zoom.gif)

_Zoom example_

### VIDEOGAMES

Here you will see only some of the transitions that we see in video games, all of them have been extracted from this [website](http://www.davetech.co.uk/screentransitions), where you can find a bunch of really good examples of camera transitions in video games.

- __Alternating bars:__ 

![Alternating Bars](https://raw.githubusercontent.com/Bullseye14/Camera-Transitions/gh-pages/Images/alternating_bars.gif)

- __Dissolve squares:__ 

![Dissolve squares](https://raw.githubusercontent.com/Bullseye14/Camera-Transitions/gh-pages/Images/dissolve_squares.gif)

- __Increasing cubes:__ 

![Increasing cubes](https://raw.githubusercontent.com/Bullseye14/Camera-Transitions/gh-pages/Images/increasing_cubes.gif)

- __Rotate cube:__ 

![Rotate Cube](https://raw.githubusercontent.com/Bullseye14/Camera-Transitions/gh-pages/Images/rotate_cube.gif)

- __Rotate screen:__ 

![Rotate screen](https://raw.githubusercontent.com/Bullseye14/Camera-Transitions/gh-pages/Images/rotate_screen.gif)

- __Squeeze scene:__ 

![Squeeze scene](https://raw.githubusercontent.com/Bullseye14/Camera-Transitions/gh-pages/Images/squeeze.gif)

## TIPS FOR CAMERA TRANSITIONS
The first important thing to be aware of is that it can look weird if you are using different transitions for every scene, as it's advisable to keep them the same style all the time.

It's not compulsory to use transitions each time you switch between scenes: if you don't want to mean something with the transition, just add a simple cut.

The best camera transitions should go unnoticed, meaning that you feel that it's all belonging to the same environment.

## HOW DOES IT WORK?

Here you will find the explanation on how this transitions are coded in C/C++, using Visual Studio.

### TRANSITION MANAGER

This module is the one that creates, contains and deletes all the transitions. When you call a transition, the transition manager creates a New Transition() and does a push_back() of it to the list of active transitions. When this transition has ended, this module removes the transition from the list and deletes it.

### TRANSITION

This is the Transitions class, and all the transitions (Fade, Wipe, Lines, etc) will derivate from this parent class. The class determinates the state of the transition (start transition, change scene and exit transition) and three functions that are called depending on the state of the transition (_void Start()_, _void Change()_, _void Exit()_). There is also another function (_Interpolation()_), where you pass two values (starting point and ending point), and the percentage, and this returns the values from the start to the end, depending on the percentage.

### EACH TRANSITION

Each transition has its own module, because the way in their change the scene is really different. In the constructor we initialize all the values that we will need to do the transition, and then we will call a Start, Change and Exit voids, if needed:

In the _void Start()_, we do the animation in order to cover all the screen with the color wanted (normally black).

In the _void Change()_, we cover all the screen with a _SDL_Rect screen_, and we change between scenes.

In the _void Exit()_, we undo the animation, that is normally doing the same as we did in the start but changing the order of the interpolation.

## TODO'S IN VISUAL STUDIO

## WEBGRAPHY

- [GIFS 1](https://www.youtube.com/watch?v=OAH0MoAv2CI)
- [GIFS 2](https://www.youtube.com/watch?v=dJ21oJURdTE)
- [GIFS 3](https://www.youtube.com/watch?v=iWGvt3KkfqU)
- [Video 1](https://www.youtube.com/watch?v=BagcGilr5vc)
- [Video 2](https://www.youtube.com/watch?v=C7307qRmlMI)
- [Documentation 1](http://www.ibuprogames.com/2015/11/10/camera-transitions/)
- [Documentation 2](http://www.davetech.co.uk/screentransitions)
- [Documentation 3](https://www.webopedia.com/TERM/S/shader.html)
- [Documentation 4](https://biteable.com/blog/tips/video-transitions-effects-examples/)

