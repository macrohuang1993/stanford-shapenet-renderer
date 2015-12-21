# Stanford Shapenet Renderer

A little helper script to render .obj files (such as from the stanford shapenet database) with Blender.

Tested on Linux, but should also work for other operating systems. 
By default, this scripts generates 30 images by rotating the camera around the object. Additionally, the depth map is dumped.

To render a whole batch, you can e. g. use the unix tool find:

    find . -name *.obj -exec blender --background --python render_blender.py -- --output_folder /tmp {} \;

To speed up the process, you can also use xargs to have multiple blender instances run in parallel using the `-P` argument

    find . -name *.obj -print0 | xargs -0 -n1 -P3 -I {} blender --background --python render_blender.py -- --output_folder /tmp {}

## Example images

Here is one chair model rendered with 30 different views:

![Chairs](examples/out_without_specular.png)
