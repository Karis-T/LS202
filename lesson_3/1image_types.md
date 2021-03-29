## Image Types

<div style="border: 1px solid grey; padding: 1% 4% 2% 5%;">
  <h6>Glossary</h6>
  <ul style="list-style: none; margin-left: -5%;">
    <li><b>Compression:</b> encodes the file to reduce its size</li>
    <li><b>Lossiness:</b> a form of compression that loses file information and quality in order to reduce the file size</li>
    <li><b>Artifacts:</b> blocky sections of color caused by compression and discarding non-essential data</li>
    <li><b>single color transparency:</b> Reserves a single color and if any pixel matches it becomes clear</li>
    <li><b>alpha color transparency:</b> adds an alpha channel to images creating upto 65536 different levels of opacity</li>
  </ul>
</div>

### JPG

- The most common image format used on the web
- highly accessible format found in design software and digital cameras
- used for photos, drawings diagrams and more
- jpgs don't suit background images as they show artifacts and visible compression
- balanced image quality vs compression
- Jpgs compression is **lossy** and you can set the compression when you save a file
  - low compression = better image but larger files
  - high compression = poorer image but smaller file
- everytime you edit a jpg it loses information and detail
- all jpgs contain **artifacts** on close examination
- aim to reduce the size of a jpg as much as possible without losing noticable detail / introducing visible artifacts. (requires experiementation per image)

### PNG

- perfect for both background and non-photographic images
- **single color** and **alpha transparency** option are great for logos, icons and lineart
- they use compression but its **non-lossy** (doesnt lose file info in order to compress image) resulting in larger files than JPGs
- ideal for images that require detail / transparency or need to support more than 16.7 million colors.

### GIF

Due to their limited 256 color palette rang, GIFs are perfect for smaller images and app icons, where size and details don't matter too much.

### Image comparison table

| **Feature**          | **JPG**       | **PNG**          | **GIF**                |
| :------------------- | :------------ | :--------------- | :--------------------- |
| Compression          | Lossy         | Non-lossy        | None/Lossy/Non-lossy   |
| Photographs?         | Yes           | Yes, but too big | No                     |
| Line Drawings?       | No            | Yes              | Depends on drawing     |
| Gradients?           | No            | Yes              | No                     |
| Typical File Size    | Small         | Medium-Large     | Tiny                   |
| Quality              | Poor to Good  | Best             | Good but limited color |
| Color Palette        | 16.7 million  | 256 TC*          | 256                    |
| Color Depth          | 24 bits       | 8-48 bits        | 8 bits                 |
| 1-Color Transparency | No            | Yes              | Yes                    |
| alpha Transparency   | No            | Yes              | No                     |
| Resolution Maximum   | 65536 x 65536 | 2 GP x 2 GP**    | 65536 x 65536          |
| Total Pixels Max     | 4 GP          | 256 EP***        | 4 GP                   |

*TC = 256 teracolors, an astonishing 280 million million colors.

**GP = refers to gigapixels

***EP = 256 exapixels, an incredibly large number: 3 followed by 23 zeros.