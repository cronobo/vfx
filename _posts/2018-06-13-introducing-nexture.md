---
layout: post
title: Introducing Nexture, the first skin microdetails baker powered by artificial neural networks
---

> This article was redacted with our partner texturingxyz

# The quest for hyperrealism of CGI human characters

From a multi-aspects point of view and for almost all departments such as modeling, animation, texturing, lookdev, rendering, etc., realism / hyperrealism is “still” something really difficult, if not almost “impossible”  to achieve when it comes to humans, simply because “realism” means to re-create reality, where, in CG we tend to only “mimic” it. There are way too many things regarding humans that our brain automatically detects as real or fake.

That’s also why major studios are working really hard to make digi doubles, most of the time using scanned data along with FACS / Mocap to get “accurate” models to work with. In this case, accurate doesn’t actually mean that it is 100% like in reality, it’s still an interpretation of all the technology that produces the digi double. Thanks to existing technology, we can achieve close to 95% true realism. But it’s that 5% left that makes CG humans look fake.

Skin structure representation in CGI has always been a huge complicated task to achieve when it comes to creating a hyper realistic character or creature that needs to be integrated into a real world environment.

We all know the “uncanny valley”, that refers to the breach between reality and CG. If you look closely at the characters made in the last 10 years, especially in movies, you will notice a huge improvement in terms of realism. That’s also because tools have evolved, technology emerged and the VFX industry has grew enormously.

In fact, more and more fully CGI characters are on screen for longer periods of time (CF : Thanos in The Avengers Infinity war), and need to be realistic and fully integrated into their environments to be convincing. With the arrival of 4k screens, the standardization of IMAX in theatre, subtlety over the details become a must, to achieve something believable and almost touchable.

[THANOS]

Following, and inspired by the great research on Micro geometry (http://gl.ict.usc.edu/Research/Microgeometry/) from Paul Debevec and his team, we decided to work closely with the Cronobo company for the past two years on an innovative and powerful AI-based tool that could generate micro maps from an existing displacement map.

[Rajouter synthesized images en bas]

The main idea was to bring a new way of generating micro maps, that could lead to a more realistic skin feel, highly improved roughness, effortlessly and accurately, based on a massive micro scans library.

For this, we, at Texturingxyz, captured over 1000 micro skin data for the whole body (~800) and face (~200) using photometric stereo principals and custom equipment, with matching Albedo, Specular and Displacement.
Each captured sample is about 6mm for 512px, which is more than enough to get the core structure of a skin pore (pattern) and let the AI tool work with it. The library is now complete and fully workable with the software.

# Synthesizing ultra-realistic textures using Artificial Neural Networks

At Cronobo, we achieved the vision of tXYZ by implementing Nexture, the first micro-details baker powered by neural networks.

Nexture can increase the level-of-details of any texture, far beyond what can be captured with even the most advanced photogrammetry rigs, while respecting the original image content and structure. Nexture does not simply apply or blend details above the existing image, it synthesizes from scratch in an iterative approach a new image that matches the content of the original one with details inspired from the pattern bank.

This feat is achieved with a powerful processing algorithm that relies at its core on a neural network. Recent advances in the field of artificial intelligence have demonstrated how neural networks can be such an incredibly powerful tool for extracting high level information from raw pixel data, such as feature extraction, image matching, image translation, separation between style & structure, and image classification. The quality of this kind of neural information helps Nexture reach such high levels of quality, and guarantees that the result will be good on a very large range of input images.

Additionally, Nexture is capable of “understanding” a translation between two images. This capability lets us for instance generate a specular and albedo map, directly from a displacement map.

Because Nexture is capable of adding details to an image, the side-effect is that it can also increase the texture resolution. It is common to increase by a factor of 4 the resolution of the displacement map, while getting a sharp output image.

Most importantly, Nexture does not try to replace Artists. Instead, artists focus on what matters, for instance designing the core features of a human face displacement map, define which kind of details must be applied on each area of the map, and let Nexture do its work and handle the time-consuming task of applying those details.

[IMG spec - albedo - dsp]

At Cronobo, our experience and skill set has enabled us not only to implement the core features of Nexture, but to make it viable for the constraints of the CGI world, such as handling huge image resolutions, applying large amount of different details on the resulting image, optimization and computation times, and much more. We believe it is the first of a new generation of tools that can do a better job at helping artists achieve their vision.

# Testing this technology

Finally, we are glad to offer this tool on-demand as a service for anyone who would like to improve and get the benefit of it.
On the other side, for companies in need to process images on premises, we offer a multi platform deployment on internal infrastructure an extensive support.
That being said, we can also help customers by reviewing their specific need, and eventually propose a custom solution.

Feel free to contact us, we would love to hear from you !

[contact form]
