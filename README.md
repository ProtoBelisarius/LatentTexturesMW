# LatentTexturesMW
4k Textures for Morrowind upscaled with the help of Stable Diffusion


Comparison of Intelligent/MET TES3 Morrowind textures and my Stable Diffusion tests(Original-Intelligent-MET-SDUpscale) - question of feasability for a 4k texture pack



My goal is to create a 4k texture pack for Morrowind that holds very close to the Original.

I upscaled some Original Morrowind Textures with Stable Diffusion, more specifically the "Ultimate SD Upscale Script" for the Automatic1111 WebUI. This combines classic GAN upscalers(like ESRGAN/SwinIR/etc) with Stable Diffusion, and as such can create new Information in a guided manner via prompt. This also removes some common problems of current upscalers, such as overpronounced clearly visible streaky lines, because Stable Diffusion reinterprets the upscaled version and makes corrections to better fit the prompt. Even with a prompt with little specificity, such as the material (wood/stone/copper/etc) and maybe the type (door/window/etc), is it possible to achieve pretty great results. It introduces a slight color shift for the whole texture (as do all upscalers), but that can be pretty easily corrected with tools like chaiNNer to do a weak run of "Average Color Fix" for the whole batch, and regain the original color without losing the detail.

It works best on textures that that dont seamlessly tile like doors.





Repeating textures such as the imperial wall textures will need to be separated from others as additional operations need to be done to them.
For  only left/right tiling textures like the wall here its possible to simply 1 and 1/4 of the texture when upscaling, and then cutting the additional 1/4 and blending it in a gradient over the other side to make perfectly tiling textures.



Faces can be upscaled as well, with either low denoise strength (for fewer changes) or with high. I currently have just played with the golden saint face for a bit, but the results arent that satisfactory. This will require further testing for better results.






To completely realize this project, all textures need to be sorted by at least material for batch upscaling, as each texture from 256x256 to 4096x4096 takes at least 8 Minutes and as such needs to run in the background/overnight.

-----> adjusting settings might bring down time per texture down to 3 min.

The file sizes might also be problematic, as converted to .dds(DXT1) they are at least 10x compared to the MET 2k textures. Im not (well(at all)) versed in the .dds file type and as such cant say anything about the different compression types and which are supported by OpenMW. So loading times might/will increase visibly, possibly? Also might need more vram, also question if the heavily compressed textures can be handled by the single engine cpu thread?

-----> either uncompressed or DXT1, BC7 doesnt work with OpenMW and it can supposedly handle 4k

Further research/testing required.
