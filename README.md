# Rain Drop Effect2: Beautiful, flexible, and faster rain distortion effect for Unity

This project enables creating a screen effect with not only rain distortion but blood effect and water effect.

![Image not found.](https://github.com/EdoFrank/bin/raw/master/RainDropEffect2/rde1.jpg)

## Feature
- Easy to use
- Dynamic and realistic distortion, fast and flexible
- DirectX9 is supported
- VR is supported

## Demo
[![Youtube video not found.](http://img.youtube.com/vi/ulWFE8J8E94/0.jpg)](https://www.youtube.com/watch?v=ulWFE8J8E94)

 [**YouTube**](https://www.youtube.com/watch?v=ulWFE8J8E94)

## How to use
Open the following demo project, and you will find how to use the project.

```
RainDropEffect2/Demo/Demo*.unity
```


## Game-in-ready prefabs
Some basic and useful prefabs are prepared for you. Please use prefabs in

```
RainDropEffect2/Prefabs
```

#### Rain
Normal rain drop effects where you can D&D the prefab(s) at your scene.

#### Blood Rain
A splash of blood

#### MobileRain
Cheap rain effects optimized for mobiles

#### Water Splash In
A water splash (diving) effect

#### Water Splash Out 
A water splash (leap out) effect

#### Frozen
This is a freezing effect in a cold environment

#### VR
VR supported effects

- If an effect is not playable at start, you have to call a method from your script as follows:

```csharp:
[RainCameraController].Refresh (); // If you need
[RainCameraController].Play (); 
```

## Customize your effect
#### RainCameraController.cs
RainCameraController.cs is a main component you'll use.
It requires an orthographic camera, or perspective view in case you use VR mode. 
When you attach RainCameraController.cs for an arbitrary game object, a camera is automatically added.
Please refer properties of RainCameraController to customize.


### Inspector Configuration

#### Render Queue
The Render Queue controls the order for effect rendering. 
If you are using GUI assets (e.g., NGUI) under RainCameraController, you can controll the queue of effects. 
3000 is a default value.

#### Alpha
You can control whole rain alpha value under the camera.

### Property

```csharp:
// It returns the current draw call RainCameraController.cs issues.
public int CurrentDrawCall {get;}

// Gets the max draw call theRainCameraController.cs issues.
public int MaxDrawCall {get;}

// It's true when rain drop controllers are playing.
public bool IsPlaying {get;}
```

### Method

```csharp:
// You can call this method when you want to redraw rain.
public void Refresh ()

// Starts the rain increasingly.
public void Play ()

// Stops the rain gradually.
public void Stop () 

// Stops the rain immediately.
public void StopImmidiate ()
```

## Note
You can optimize performance using low scale rain drop normal map.
Do not forget to adjust the resolutions too. In some case, resolutions on mobile platforms are too high.
