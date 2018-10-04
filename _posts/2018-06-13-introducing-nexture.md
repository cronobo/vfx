---
layout: post
title: Introducing Nexture, the first microdetails synthesizer powered by artificial neural networks
---

![3D Render before and after processing displacement map with Nexture](/assets/banner-normal-spec.jpg)

# Reaching photorealism for computer-generated human characters

The “[uncanny valley](https://en.wikipedia.org/wiki/Uncanny_valley)” is a popular concept that highlights the barrier between reality and computer-generated imagery ([CGI](https://en.wikipedia.org/wiki/Computer-generated_imagery)). It states in particular that photorealistic characters either look real, and you forget about it, or they look fake and weird. There is no middle-ground.

Therefore, major studios work really hard to create digital actors that perform in 3D-rendered movies and sequences.
Those digi-doubles contain **volume**, **surface**, and **motion** information required for the acting and rendering.

In this article, we focus on the **surface** information, that is usually obtained through photogrammetric scanning and manual work. More specifically, **human skin surface** is tough to represent in CGI, and remains a true challenge for ultra-realistic characters that integrate seamlessly into their environment.

Using photogrammetric scans directly can provide very highly detailed texture, but offer no intrinsic flexibility.
Any manual modification, to add or remove wrinkles at desired location for instance, is a nightmare to do, because exactly of the level of detail. Any major modification of the map will also require updating all level of details.
Think of it as if you are asked to reshape a mountain, and you have to move every single rock on it to keep the result real.

Another approach consists in scraping parts of multiple scans, and placing them together to form the final texture.
This approach offers more flexibility and constraints less the artist, but presents one intrinsic issue : stitching.
All those patches need to be stitched together so that the resulting map becomes seamless.
This is usually achieved some form of transparency and blurring, which, ultimately, results in a loss of quality.

Therefore, there is a need for a new approach that would still give full flexibility to the artist, while being able to produce **seamless**, high-quality maps, out of the box. At Cronobo, we have developed a new tool, called Nexture, to solve this issue.

# Nexture

Nexture is the fruit of a large effort of research and development, and is the combination of multiple advances in the field of artificial neural networks, human skin capture and human skin representation

![Preview of Nexture on displacement map](/assets/crops_gif.gif)

At its heart, Nexture can synthesize any image (*pattern*) onto any other (*input*) image.

The result maintains the structure of the input, while having appearance and style of the pattern.
The synthesis is not just a matter of adding the pattern on top of the input.
Pattern "lock" on the existing structure, matching perfectly and in an organic fashion.

The images below were generated with Nexture, in 5 mins (the original map is 2000 pixels wide by 1000 pixels high), by changing the applied pattern:

![Multiple pattern on same image](/assets/comp_all_gif.gif)

One application of this technique is therefore to synthesize ultra-detailed patches of human skin, on top of an average human skin texture.

It is ideally suited for refining existing human skin textures to an upper level, while providing a lot of control to the artist on the visual output. The generation of details makes it possible to increase the definition of a displacement map by a factor of 4 and above.

![Increasing image definition with Nexture](/assets/nexture_process.png)

Nexture has many features that would be hard to cover in a single article, but one of them is worth mentioning.
This feature is the capability to use many different patterns, on the same image, and still obtain a seamless image out of the box. This feature alone has the potential to profoundly change the approach for creating human skin textures.

![Turning a noise into a skin pattern](/assets/noise_transform.gif)

# A combination of data, algorithms and neural networks

To fuel the software, we have captured human skin microstructure at an unprecedented level, using regular photogrammetric technique, but with a custom-built shape-from-shading surface reconstruction technique.

The current dataset comprises 50 samples, and is in the process of being expanded to 200, to cover all a majority of variations found on actual human skin.

![A few examples of the skin microgeometry dataset](/assets/patterns_filigrane.jpg)

This library is included by default in Nexture. The combination of this high-quality dataset and the robust algorithm that is at the core of Nexture provides high-quality, reliable results, on a very wide range of different textures and images.
Below is a preview of what Nexture can do on an existing 3D model:

![3D render result](/assets/before_after_gif.gif)

We have taken great care of making Nexture viable for the CGI field, and accounting for constraints in terms of image definition and quality. We believe it is the first of a new generation of tools that can do a better job at helping artists achieve their vision.

# Getting access

Nexture is currently entering beta release for studios, and it will become more broadly available in the coming months.

# Credits

A big thanks to Nicolas Collings ([nicolascollings.com](nicolascollings.com)) for the beautiful 3D renders. 
