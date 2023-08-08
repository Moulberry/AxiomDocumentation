# Distort

The **Distort** tool uses a concept called ‘Domain Distortion’ with a Simplex noise in order to distort a given area. What this does in practice is making areas more bumpy. This can help to make flat areas have more depth and texture or be used to add some bumps and carvings into more refined terrain. It does this inside the brush stroke path which can be defined by the brush settings.

The distortion can be configured further to finetune how you want to distort the terrain. The scale sets the scale of the Simplex noise used to perform the domain distortion. This can be configured to larger sizes should the scale not be large enough. It can also be configured with the seed to use different or random seeds.

The distance of the distortion increases the range in which the noise distorts. A distance of 2 being an average of 2 blocks distance away from the target position. Due to to the fact that the noise is continuous the range can be set to non-full numbers in order to finetune the range, sometimes making larger dents or bumps appear as a result. A high distance will cause it to look more ‘severe’. These distances can be separated per axis by toggling the ***Separate Axis** button

The smooth edges option blends the edges of the noise into the existing terrain to avoid jagged edges and sharp contrasts from appearing between the distorted areas.
