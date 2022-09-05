# Stable seed for Stable Diffusion

*Disclaimer: this is just a fun experiment, if you are interested in Stable Diffusion or want to know more about it, 
check out [official repository](https://github.com/CompVis/stable-diffusion) or one of the many forks. 
This is a fork of [lstein/stable-diffusion](https://github.com/lstein/stable-diffusion).*

## Seed

As you know, in Stable Diffusion for every seed value you get a unique image. 
Even slight change in the seed or resolution gives a completely different result. 
But what if you want only a slight variation. Or maybe you want to change framing, 
or even change resolution because your subject is cropped?

If we assign each seed a coordinate on a plane, then we can shift the image on it by changing the seed.  
The relevant code [is here](https://github.com/kalikin/stable-seed/blob/main/ldm/simplet2i.py#L635-L676). 
It's pretty simple, but of course, it is incompatible with the original Stable Diffusion seed.

## Examples

**Example 1**

https://user-images.githubusercontent.com/7532150/188506202-f72bfec2-5b1f-4e07-8f72-3f987d0fa22d.mp4

**Example 2**

https://user-images.githubusercontent.com/7532150/188506230-e2452582-af49-40f1-a996-9e226b356068.mp4

**Shift vertically**

https://user-images.githubusercontent.com/7532150/188506267-50eb6d6e-e33f-4e36-b8ba-afadf2509636.mp4

**Changing resolution and shifting**

https://user-images.githubusercontent.com/7532150/188506278-16e383e0-0196-4b1e-867c-2d73be52aabf.mp4


## Running the repo

If you want to run the code, check out the original [README](README-lstein.md).

In this fork, changing the seed by `+1` shifts image to the left, and by `-1` to the right, in the range `0 - 999,999`.   
The "seed plane" is `1,000,000` blocks (i.e. seeds) wide, that is, to shift image vertically, 
change the seed by `1,000,000` in the range `1,000,000 - 4,294,000,000`.
