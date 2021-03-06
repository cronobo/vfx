---
layout: post
title: Groundbreaking progress - Discover how the Nexture engine was upgraded to a whole other level
---

# The search

At Cronobo, we feel Nexture will be a key component of future texture productions workflows, because it features unique image-generation capabilities with this type of potential.

However, something was bothering us since several months now.

Despite the very positive feedback we've received with several VFX studios, **we were not satisfied with the quality**.
The generated maps looked good when used as bump maps in 3D renders, but we felt there was a lot more that could be done.

# The plan

We started a tedious process to review the entire core technology, checking each single line of code.
The goal: searching for potential improvements or sneaky bugs.

We have also trained and tested over 30 (!) different neural networks architectures.
This process spanned over several months, and we figured out a lot more about texture synthesis in the process, what architectures and settings work best, etc.

Last week, after compiling all those insights, we had identified in total two bugs and three critical changes that had the potential to increase the quality of the results by several orders of magnitude, and far beyond what can be achieved by any manual approach ; whether it's applying tileable detail layers, or manual sculpt.

While I cannot reveal the particular changes, they involved overall to change the neural network architecture, a few settings inside the architecture itself, and also radically change the way we train it. While that may seem like a lot, the neural net is actually just a part of Nexture, and is not solely responsible for generating images.

To test Nexture, we have built over the years an automated test pipeline that runs over 800 unit tests, and performs about 15 complete image synthesis to validate the behavior.

Among those tests, one of them configures Nexture to perform a Texture-transform synthesis (you'll hear more about this in the future). This is a good benchmark of the visual quality, because it is more difficult to achieve than details-transfer.

The idea is simple. We start with an actual reference picture (of the beautiful city of Toulouse, France):

![Picture toulouse](/assets/toulouse_v2.jpg)

A reference overlay is painted roughly on top of the picture:

![Reference overlay](/assets/overlay.jpg)

A second overlay is drawn, with different positioning of rivers, neighborhoods and trees.

Then, and this is where the fun starts, with this new overlay, we ask a simple question - *What is the new city image that matches this new overlay ?*

![New overlay](/assets/new_overlay.jpg)

... and we let Nexture answer.

# Old vs New version

**With the old version**, this is what was the best that could be generated with many different settings and tweaks:

![Result with old version](/assets/old_nexture_version.jpg)

Last Thursday, all the fixes and improvements were finally implemented. Immediately, the test pipeline started and we were monitoring it, hoping for a breakthrough.

With this **new version**, this is what happened:

![Result with new version](/assets/new_nexture_version.jpg)

I can't tell you how excited we were when we first saw this.
**The sharpness and fidelity of the new version is just insane** compared to the previous one.
And we're not even using the highest quality settings.

With a simple setting change (changing a single layer in the neural network), another version is obtained that produces more realistic trees but has less accurate colors (another lead to explore to get the quality even further):

![Result with new version](/assets/new_nexture_version_other.jpg)

Overall it's very promising, but it's not human skin textures.
Time for some more tests !

# Human skin texture (bump map)

Immediately, a more practical test is started.
Nexture is configured to synthesize details on a human skin displacement map.

Below is a closeup of the input map, drawn with ZBrush. As you can see, there isn't much on it.

![Original map](/assets/newversion/original.jpg)

With the **old version**, the image below was the best we could obtain:

![Old version](/assets/newversion/previous_result.jpg)

With the **new version**, this is what we get at first trial:

![New version](/assets/newversion/new_result.jpg)

Once again, we are not disappointed. The improvement is very big and noticeable.
Want to see more ? So did we !

This is another closeup, with another pattern (pattern s6):

![Original map](/assets/newversion/other_crop/preview.jpg)

**old version**:

![Old version](/assets/newversion/other_crop/old.jpg)

**new version**:

![New version](/assets/newversion/other_crop/new.jpg)

In the new image, details perfectly integrate with the original map.
The details have a lot of variation and flow naturally on the texture.
As you may have noticed, they expand, contract and follow the original map.

*NOTE*: There are some noticeable bumps on the last image, that do not feel natural.
It's an issue that comes from the reference pattern and not the software itself. They are pretty easy to remove and we're currently working on cleaning up the dataset to remove unwanted features. It was an area that has been neglected in the past due to a lack of time, but it's going to get fixed pretty soon !

**We believe these new capabilities are truly outstanding**, and set new standards for producing ultra detailed textures.

Clearly, this behavior is impossible to match with any manual approach, based on tileable details maps for instance, unless by spending an enormous amount of time placing patterns - which is neither fun nor doable.

And as you can imagine, we are also very excited about the new Texture-transform mode and we're sure it will open up new innovative ways to produce textures.

![Total mode](/assets/total_gif.gif)

# Next on the roadmap

Although we've reached a milestone, the quest for more quality is not over.
There are many areas we are researching to take it even further.
We have also kickstarted the development of a proper interface to make Nexture a regular desktop application, that will make it more accessible and even more fun to use.

In the meantime, Nexture is also available **[directly through your browser](https://cronobo.com/products/nexture/online){:target="_blank"}**, letting anyone test the technology (**including a free mode**) and synthesize micro-details maps (with the same quality but a limited set of features in a first time).

![New approach](/assets/new_version.gif)

We're also researching exciting technologies in more diverses VFX/Video Games fields, such as Lighting and Texture compression. Stay tuned for what's coming next !
