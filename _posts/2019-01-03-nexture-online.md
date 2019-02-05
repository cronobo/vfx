---
layout: post
title: Announcing Nexture Online - AI-powered microdetail layers generation, straight from your browser
---

While Nexture for Studios is currently beta-tested in some large VFX studios, at Cronobo we have been thinking for a while abount how to open up the technology to everyone, in an easy and user-friendly way.

After a few months of hard work, we are proud to officially release **[Nexture Online](https://cronobo.com/products/nexture/online){:target="_blank"}**, a tool capable of **generating a batch of detail layers from any texture**, using Artificial Intelligence.
These layers simplify greatly the detailing work on any texture, because they give the artist a convenient variation of detail layers, from the same source image. Basically, they give ultra high quality matter to work from.

*Pattern s3 - scale 0.5*
![s3 0.5](/assets/parametric/nexture_preview_s3_0p5.jpg)

*Pattern s1 - scale 0.5*
![s1 0.5](/assets/parametric/nexture_preview_s1_0p5.jpg)

*Pattern s5 - scale 0.5*
![s5 0.5](/assets/parametric/nexture_preview_s6_0p5.jpg)

Since **all detail layers match the structure of your texture**, producing a final, highly-detailed map is super easy.
Simply use any of the generated maps directly, or if you want more variations, mix multiple maps together with clipping masks for instance.

# Usage

The tool is directly available from your browser, requires no signup and is super easy to use.
Behind the scene, it operates our Nexture technology on latest cloud GPUs to make sure you get your maps rapidly and with the best quality.

![Monkey gif](/assets/monkey.gif)

Our goal with Nexture Online is to help small studios, freelance & individual artists accelerate the process of making photorealistic organic textures, by automating the generation of details on displacement maps.


The tool is focused on ease of use:

- it is directly accessible through a browser,
- it requires no installation, no signup,
- it takes 2 minutes to launch a synthesis

The interactive UI lets you look around, zoom in and out around your map, to check if the details settings suit you.

![Nexture Online UI demo](/assets/ui_nexture_online.gif)

The blue-ish microdetails image overlayed over your map **is just a preview**.
It helps you pick the pattern and set the scale.
The synthesized image has none of the artifacts presents on the preview, is perfectly seamless and is greyscale, not blue.

You can upload an image in PNG, JPG or TIFF format, up to 1GB, with a resolution of up to 8k. That should fit most use-cases nicely.

A total of 63 human skin patterns are available, selected for their variety and interest.

Therefore, you can synthesize details on any map of yours, using this collection of patterns.
For each pattern, you can change the scale, to have details fit nicely with what is already into your map.

# Why the browser ?

Some of you may be surprised to see this product available through a web-browser.

This choice was motivated by a willingness to set everyone on equal footing, and avoid frustrating users with a technology we believe to be the future of texture creation.

As with any technology that runs intensive AI computations, Nexture requires a powerful GPU to operate.
Some folks do have the hardware to run it, but not everyone because this stuff is expensive.
Also, GPUs are improving quickly, and become quickly deprecated for AI-based applications.

By offering this product through a browser, we are able to leverage the extraordinary hardware that is offered by Cloud providers.
Every job launched through **[Nexture Online](https://cronobo.com/products/nexture/online){:target="_blank"}** runs on an Nvidia Tesla V100, [one of the most powerful GPUs on the planet](https://www.nvidia.com/en-us/data-center/tesla-v100/).

Therefore, by offering this product through a browser, we are able to give anyone access to the best hardware at a very affordable price.

![Nexture Online applied onto a skin displacement map](/assets/synthesis_nexture_online.gif)

We also know some people do not want to run stuff in the cloud. For this purpose, we will be opening our Studio version to Freelancers once we develop a clean User Interface (UI) up and running.

# Roadmap

This tool is still in beta, and we'd love to get your feedback. You can reach us at [contact@cronobo.com](mailto:contact@cronobo.com) or via [cronobo.com](https://cronobo)'s help chat.

Some features are still missing compared to the Studio version, namely:

- more supported image formats
- more patterns (and importing your own !)
- lower price tier for testing on a large range of settings

Also, to fit all the data required for synthesis inside GPU memory, there are some settings on our core algorithm we had to set to minimum. The quality even with those minimum settings is already amazing, but as we improve the software's performance and as hardware progresses, we'll be able to increase quality settings even further and obtain very incredible synthesized maps.

Finally, our internal pattern-capture pipeline improves every day, whether it's the hardware or the post-processing.
Thanks to our core software-background, we can leverage image processing algorithms that are simply not available in any commercial products, and even roll out our own solutions.

On a more broad topic, we have multiple new technologies that are now going under a strong R&D effort, and multiple neural networks in training as I write. Stay tuned !

*Note: We've achieved some [major quality upgrade](/2019/02/02/groundbreaking-progress.html) since this article was written down. Check it out !*
