---
layout: post
title: A pre-release review of Nexture
---

As Nexture is nearing beta release, it is now a good time to show how this application can be used to create images and textures in new innovative ways.

So far, we have mostly talked about [human skin](/2018/06/13/introducing-nexture.html).
Human skin is an incredible topic of research for 3D rendering.
However, Nexture is not only about human skin texture. *Very far from it.*

Nexture is about producing images in a **modular** approach, faster and with very high quality.
Fundamentally, Nexture can synthesize any amount of patterns, on any image, **seamlessly**.

## Seamless Textures

Creating a texture often involve scraping parts of other sources (such as reference images, photogrammetric scans, etc.) and combining those bits together. Then comes the tricky part of making all those parts stitch properly.

![Patterns stitching](/assets/patterns_stiching.png)

Filling this gap is not obvious at all.
And it's also not easy when you have dozens of different textures to stitch.

This is where Nexture can help. See below what gets synthesized after 1.5 hours of computation (original image is 4k wide):

![Patterns stitching](/assets/patterns_stiching.png)

The image has zero artifacts at the boundary. And yet, this is a very, very challenging boundary to solve.

Imagine the possibilities on the displacement map with 30 different patterns, where you previously had to spend a considerable amount of time making everything fits.

Now, your map is seamless, **out-of-the-box**.

To generate this image, we start by defining two patterns. For the sake of this concept example, patterns are simplistic images, but in practice, a pattern can be any image. Displacement map, specular, albedo and normal maps are all ideally suited for Nexture.

![Samples](/assets/samples.png)

Then, we simply define where each pattern should be applied, inside a vector file (standard [SVG](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics) file, that can be edited with [Inkscape](inkscape.org), Illustrator, etc).

![Placement of patterns](/assets/circle_square_placement.png)

This is a very simple example, yet it demonstrates already how a solid algorithm and a well-trained neural-network can help artists reach their visual goals. To see a more realistic example, please check out our [previous blog post](TODO).

Now, placing patterns on the image is only part of the fun.

### Guiding structure

In the previous example, the input image was blank.
But it's way more interesting to provide an input image with some (or even a lot) of existing structure.
Synthesized patterns are going to incorporate it in the image.

![](Image with structure)

For this image, we have used the pattern below (that is part of the default dataset of Nexture). It contains information about specular, albedo and displace, but only displacement was used so far.

![](Pattern s51)

### Cross-synthesis

What about creating both a displacement map and its specular ? Nexture do that too.

![](Image with structure disp)
![](Image with structure specular)

### Scale

You can change the scale of the patterns.

![](Image with different scale)

### Transition width

You can set a different width for the transition area, to make the transition more or less strong.

![](Image with different transition width)

## Modularity

Nexture basically lets you create an image from a library of pattern.
In the long, the idea is that Freelance artists and Studio will create their own libraries.
This is an incredibly strong technique, because reusable processes yield significant time savings.
And with this approach, you are not sacrificing anything on quality nor flexibility.


IMAGE library

Creating the last level of detail of any texture by hand is a very time-consuming task.

Often, the workflow involves placing by hand bits of scanned textures, and stitching those patches together so that the final result looks decent. The more details you want, the more challenging it becomes.
Because individual patches do not share the same underlying structure, it is necessary to rely on hacks like blending and alpha maps to produce somehow seamless images. And this is done at the expense of the final quality and level of details of the map.

As texture dimensions and quality requirements increase, this approach does not scale anymore.

Nexture aims to offer a new workflow to remove this issue.
Instead of having to do all the detailing work by hand, artists can focus on the fun stuff, basically creating the main features of the image, and leave the repetitive and time-consuming task of detailing work to the application.

IMAGE STRUCTURE vs STRUCTURE + DETAILS

## The workflow
