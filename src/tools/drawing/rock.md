# Rock

The **Rock** tool is a noise-based sculpting tool useful for making rock-like terrain and shapes. It can be used for both individual rocks and boulders as well as making surfaces look more rocky and rough. It uses several parameters that change how rocks form in general as well as in relation to the surface they’re placed on. It uses the active block to determine the palette. Various settings are available to finetune the tool’s sculpting behavior:

## Noise Settings
 The noise settings lets the user configure how random and rough the rocks created by the sculpting tool should be. There are several settings that can be adjusted to change the noise’s behavior. 

The noise radius is a setting that determines the 'scale' of the noise-induced modifications. A larger noise radius implies a broader impact zone, affecting more blocks, which in turn forms bigger, blob-like configurations that are typically more rounded and smoothed out due to the wider distribution of changes. On the other hand, a smaller noise radius, which affects fewer blocks, will result in more refined and jagged alterations, constrained by the voxel grid size.

The ‘Noisiness’ slider affects how ‘noisy’ or random the sculpted blocks will be. A higher level of noisiness yield more random and blobby looking rocks. A lower level of noisiness yields more smooth spherical rocks. Combined with the noise radius and other factors this can impact how rough the rocks’s final appearance will be. 

The Noise Field Seed lets you enter a seed should you want to continue a pattern that you previously used or reuse after playing with parameters, by default it is randomized on every stroke.

## Smoothing Settings
The smoothing settings affect how much the rocks produced by the previous settings get smoothed out in order to create a more coherent and unified looking rock shape rather than being floating blobs. 

The Smoothing Standard Deviation settings let you set the strength of the Gaussian blur applied to the tool. The default ranges from 0 to 5 but can be extended beyond the cap. 0 being equivalent to having no smoothing applied, 2 - the standard setting - being equivalent to having roughly ~4 blocks of range of smoothing and 5 being very smooth with a range of roughly ~10 blocks of smoothing.

The Meld strength is a feature that lets you determine how strongly a rock should be melded or belnded together with the existing blocks of the world. This causes rocks to smooth out more near the edges of the brush in order to ease out the jagged edges that a rock might otherwise have. The default ranges from 0 to 3 but can be extended beyond the cap, 0 having no melding applied and just being placed at the surface, 3 being a strong melding affect. The meld strength is also affected by smoothing, with more smoothing causing ‘melded edges’ to be more finely smoothed into the existing blocks.

