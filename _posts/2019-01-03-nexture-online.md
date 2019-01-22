---
layout: post
title: Announcing Nexture Online - skin microdetails synthesis, directly through your browser
---

While Nexture for Studios is currently beta-tested in some large VFX studios, we at Cronobo wanted to open up the technology to everyone.

After a few months of hard work, **we are proud to officially release [Nexture Online](https://cronobo.com/nexture-cloud){:target="_blank"}**, a skin microdetails synthesizer directly available through your browser.

![Nexture Online applied onto a skin displacement map](/assets/synthesis_nexture_online.gif)

Our goal with Nexture Online is to help small studios, freelance & individual artists accelerate the process of making photorealistic organic textures, by automating the generation of details on displacement maps.

# Usage

The tool is focused on ease of use:

- it is directly accessible through a browser,
- it requires no installation, no signup,
- it takes 2 minutes to launch a synthesis

The interactive UI lets you look around, zoom in and out around your map, to check if the details settings suit you.

![Nexture Online UI demo](/assets/ui_nexture_online.gif)

The blue-ish microdetails image overlayed over your map **is just a preview**.
It helps you pick the pattern and set the scale.
The synthesized image has none of the artifacts presents on the preview, is perfectly seamless and is greyscale, not blue.

You can upload PNG, JPG and TIFF images, up to 1GB, with a resolution of up to 8k. That should fit most use-cases nicely.

There is a collection of 63 human skin patterns available, that were selected for their variety and interest.

Therefore, you can synthesize details on any map of yours, using this collection of patterns.
For each pattern, you can change the scale, so that details that integrate nicely into your map.

After synthesis, you end up with one or more maps, each corresponding to your texture but with a different pattern:

![s3 0.5](/assets/parametric/nexture_preview_s3_0p5.jpg)

![s1 0.5](/assets/parametric/nexture_preview_s1_0p5.jpg)

![s5 0.5](/assets/parametric/nexture_preview_s6_0p5.jpg)

The images above give you a good example of the diversity you can generate from a single displacement map.

You can then blend all different textures together, by applying a mask to each texture and merging them together for instance.
This workflow lets you adjust the result inside your favorite texturing tool until you're pleased with the visual aspect of your 3D render.

Then, we recommend blending this details map with your original displacement map, to adjust to importance of details vs large-scale features. You can check out Pixar's RenderMan [tutorial](https://cronobo-staging.firebaseapp.com/nexture-cloud) on photorealistic heads that includes maps from Cronobo to understand the whole process.

# Why the browser ?

Some of you may be surprised to see this product available through a web-browser.

This choice was motivated by a willingness to set everyone on equal footing, and avoid frustrating users with a technology we believe to be the future of texture creation.

As with any technology that runs intensive AI computations, Nexture requires a powerful GPU to operate.
Some Freelance artists do have the hardware to run it, but not all because this stuff is expensive.
Also, GPUs are improving quickly, and become quickly deprecated for AI-based applications.

By offering this product through a browser, we are able to leverage the extraordinary hardware that is offered by Cloud providers.
Every job launched through Nexture Online runs on an Nvidia Tesla V100, [one of the most powerful GPUs on the planet](https://www.nvidia.com/en-us/data-center/tesla-v100/).

Therefore, by offering this product through a browser, **we are able to give anyone access to the most advanced hardware, for the price of a texture**.

![Monkey gif](/assets/monkey.gif)

# Roadmap

This tool is still in beta, and we'd love to get your feedback. You can reach us at [contact@cronobo.com](mailto:contact@cronobo.com) or via [cronobo.com](https://cronobo) help chat.

Some features are still missing compared to the Studio version, namely:

- more supported image formats
- placing multiple patterns with different locations

Also, to fit all the data required for synthesis inside a GPU, there are some settings on our core algorithm that had been set to minimum. The quality even with those minimum settings is already amazing, but as we improve the software's performance and as hardware progresses, we'll be able to increase quality settings and obtain very incredible synthesized maps.

Finally, our internal pattern-capture pipeline improves every day, whether it's the hardware or the post-processing.
Thanks to our core software-background, we can leverage image processing algorithms that are simply not available in any commercial products, and even roll out our own solutions. 

On a more broad topic, we have multiple new technologies that are now going under a strong R&D effort, and multiple neural networks in training as I write. Stay tuned !
