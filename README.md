# Advanced modelling and animation report

## 1. Model and animation

For this project, I decided to create a bird with a simple flying animation. The bird would be used in the Flying Whale game as a prop.

I began by sculpting the bird's body using Zspheres. I then added some muscular detail to the body and made the head and beak.

![body](https://user-images.githubusercontent.com/32599151/37866565-40b0c3f8-2f84-11e8-8f12-b262841b50b9.png)

Afterwards, I added a plane and drew the shape of the wings using a mask.

![wingmask](https://user-images.githubusercontent.com/32599151/37866567-54ebd95c-2f84-11e8-8b48-c482ac6ce3c2.png)

I extracted the wings from the plane and added some detail.

![wing extract and detail](https://user-images.githubusercontent.com/32599151/37866574-6e69b8fe-2f84-11e8-9d9e-b323f5c206a9.png)

Lastly, I pulled the toes and tail from the body shape. Then I merged the wings.

![divided](https://user-images.githubusercontent.com/32599151/37866584-950fc4ee-2f84-11e8-9c01-7d5e186b00f3.png)

![bacl](https://user-images.githubusercontent.com/32599151/37866613-fe8602ee-2f84-11e8-8187-05e713e82ce2.png)

Once the sculpt was finished, I then imported the high poly mesh into Maya for retopology. I first retopologized half of the model using the quad draw tool.

![half retopo](https://user-images.githubusercontent.com/32599151/37866626-2a193458-2f85-11e8-88e8-da6960979959.png)

Then, I mirrored the created polygons and smoothed the model.

![retopo mirror](https://user-images.githubusercontent.com/32599151/37866629-46d4cad0-2f85-11e8-99ea-9c95213e86e5.png)

![retopo smooth](https://user-images.githubusercontent.com/32599151/37866631-4985a790-2f85-11e8-8e68-c29b55d0a30f.png)

With the low poly model ready, I then exported it into Blender for UV mapping.

![uv map](https://user-images.githubusercontent.com/32599151/37866703-2c420772-2f86-11e8-937d-26318c62086a.png)

I assigned different materials to different faces of the mesh. I then baked those materials into an ID map.

![idmapbird](https://user-images.githubusercontent.com/32599151/37866717-50d7079a-2f86-11e8-842b-8b00bff30d87.png)

With the ID map set up, I could then just leave the model with a single material which would contain the information for the entire mesh.

I then exported the UV mapped model back into Maya and rigged it.

![rig1](https://user-images.githubusercontent.com/32599151/37866645-776d626a-2f85-11e8-92cb-6af15c5350db.png)

![rig2](https://user-images.githubusercontent.com/32599151/37866646-797b8fb4-2f85-11e8-9f8f-81823b39e4a1.png)

After painting weights, the next task was to animate. However, the bone hierarchy was not set up properly. All the joints were children of their controllers, instead of keeping the hierarchy clean and using constraints. As suggested, I duplicated the wrong rig and cleaned up the hierarchy. Afterwards, I attached the new hierarchy to the bird model and used constraints connected to the previous rig. Therefore, I was able to fix the joint hierarchy without losing the animation.

The final animation can be seen here:

https://www.youtube.com/watch?v=IlA68oDsOjg

I then took the model into Substance Painter for texturing. Since the bird would be a simple prop in the game, the texturing was kept at a very simple level.

I baked the textures using the high poly model to have a little more detail on the textures. I then added a mask with color selection in order to use the ID map to paint the different areas of the bird.

![texture](https://user-images.githubusercontent.com/32599151/37866768-0cc0f916-2f87-11e8-9051-1f9e6c5e1495.png)

Having the model retopologized, animated and textured, I then imported it into Unreal.

![unreal import](https://user-images.githubusercontent.com/32599151/37866789-4dafd6c2-2f87-11e8-89ea-0899c0d12e61.png)

For the behavior of the bird, I first added a script which would speed up the animation by a random factor for a short period of time. I did this so that I could create flocks of birds whose flying cycles wouldn't be perfectly synchronized. I then added a timeline and made the bird move along a looping spline. The spline is easily adaptable for whatever scale the game ends up being.

The final result can be seen here:

https://www.youtube.com/watch?v=lxUaIiLs8zY

