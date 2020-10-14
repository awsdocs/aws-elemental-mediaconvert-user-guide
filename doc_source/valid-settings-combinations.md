# Valid settings combinations<a name="valid-settings-combinations"></a>

Use this table to confirm that the scan type settings you intend to use are valid together and that they work with the scan type of your source input\.

**Note**  
**Deinterlace algorithm** doesn't appear in this table, because whenever it makes sense to enable **Deinterlacer**, you can choose any value regardless of your other settings\.


| To convert this input | To this output | Use these settings values | 
| --- | --- | --- | 
|  Progressive  |  Progressive  |  **Deinterlacer**: Disabled **Deinterlace control**: N/A **Deinterlace mode**: N/A **Interlace mode**: Progressive \(default\) **Telecine**: None \(default\)  | 
|  Interlaced  |  Progressive  |  **Deinterlacer**: Enabled **Deinterlace control**: Either value **Deinterlace mode**: Deinterlace \(default\) **Interlace mode**: Progressive \(default\) **Telecine**: None \(default\)  | 
|  Hard telecine  |  Progressive  |  **Deinterlacer**: Enabled **Deinterlace control**: Either value **Deinterlace mode**: Inverse telecine **Interlace mode**: Progressive \(default\) **Telecine**: None \(default\) **Frame rate**: 23\.976  | 
|  Hard telecine  |  Progressive *When you want to use **Adaptive** for **Deinterlace mode***   |  **Deinterlacer**: Enabled **Deinterlace control**: Normal **Deinterlace mode**: Adaptive **Interlace mode**: Progressive \(default\) **Telecine**: None \(default\) **Frame rate**: 23\.976  | 
|  Soft telecine  |  Progressive  |  **Deinterlacer**: Disabled **Deinterlace control**: N/A **Deinterlace mode**: N/A **Interlace mode**: Progressive \(default\) **Telecine**: None \(default\) **Frame rate**: 23\.976  | 
|  Multiple inputs, some interlaced and some progressive   |  Progressive  |  **Deinterlacer**: Enabled **Deinterlace control**: Normal **Deinterlace mode**: Adaptive **Interlace mode**: Progressive \(default\) **Telecine**: None \(default\)  | 
|  Progressive  |  Hard telecine  |  **Deinterlacer**: Disabled **Deinterlace control**: N/A **Deinterlace mode**: N/A **Interlace mode**: Any value except progressive **Telecine**: Hard **Frame rate**: 29\.97  | 
|  Hard telecine  |  Hard telecine  |  **Deinterlacer**: Disabled **Deinterlace control**: N/A **Deinterlace mode**: N/A **Interlace mode**: Any value except progressive **Telecine**: None **Frame rate**: Follow source  | 
|  Soft telecine  |  Hard telecine  |  **Deinterlacer**: Disabled **Interlace mode**: Any value except progressive **Telecine**: Hard **Framerate**: 29\.97  | 
|  Multiple inputs, some interlaced and some progressive   |  Hard telecine  |  **Deinterlacer**: Disabled **Deinterlace control**: N/A **Deinterlace mode**: N/A **Interlace mode**: Any value except progressive **Telecine**: Hard **Framerate**: 29\.97  | 
|  Interlaced  |  Interlaced  |  **Deinterlacer**: Disabled **Deinterlace control**: N/A **Deinterlace mode**: N/A **Interlace mode**: Any value except progressive **Telecine**: None  | 
|  Multiple inputs, some interlaced and some progressive   |  Interlaced  |  **Deinterlacer**: Disabled **Deinterlace control**: N/A **Deinterlace mode**: N/A **Interlace mode**: Any value except progressive **Telecine**: None  | 
|  Progressive  |  Soft telecine  |  **Deinterlacer**: Disabled **Deinterlace control**: N/A **Deinterlace mode**: N/A **Interlace mode**: Any value except progressive **Telecine**: Soft  | 
|  Hard telecine  |  Soft telecine  |  **Deinterlacer**: Enabled **Deinterlace control**: Either value **Deinterlace mode**: Inverse telecine **Interlace mode**: Any value except progressive **Telecine**: Soft **Framerate**: 23\.967  | 
|  Hard telecine  |  Soft telecine *When you want to use **Adaptive** for **Deinterlace mode***  |  **Deinterlacer**: Enabled **Deinterlace control**: Normal **Deinterlace mode**: Adaptive **Interlace mode**: Any value except progressive **Telecine**: Soft **Framerate**: 23\.967  | 
|  Soft telecine  |  Soft telecine  |  **Deinterlacer**: Disabled **Deinterlace control**: N/A **Deinterlace mode**: N/A **Interlace mode**: Any value except progressive **Telecine**: Soft  | 
|  Multiple inputs, some interlaced and some progressive   |  Soft telecine   |  **Deinterlacer**: Enabled **Deinterlace control**: Normal **Deinterlace mode**: Adaptive **Interlace mode**: Any value except progressive **Telecine**: Soft **Framerate**: 23\.967  | 