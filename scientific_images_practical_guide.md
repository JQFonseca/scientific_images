# Why the Format, Size and Resolution of Your Scientific Images Matter

## A practical guide for researchers

Every year, researchers end up with massive presentation files, thesis documents that lag or crash word processors, and manuscript figures that turn into pixelated messes during submission. The cause is usually the same: raw, unoptimised images are placed directly into slides or documents in the hope that the software will handle them appropriately.
Taking control of your image workflow does more than prevent software crashes. It solves two important sharing problems:

- **Shareability:** Unoptimised files quickly become too large to send by email or upload to repository and journal portals. Appropriately sized images produce lightweight documents that are easier to distribute.
- **Accessibility:** Colleagues, supervisors and conference audiences may view your work on mobile devices, modest laptops or slow internet connections. Properly prepared files open quickly without overwhelming the hardware. 

The benefits are practical. You collaborators can reuse your slides, images and documents with having to reconvert them or lose detail. PowerPoint files remain responsive and pleasant to edit and present. Thesis documents remain usable in Word, and the resulting PDFs can be small enough to circulate by email. Figures also survive journal submission systems with fewer unpleasant surprises.

> **Core principle:** Always retain the best editable or original version of an image as the **master**, then deliberately export different versions for specific destinations such as papers, presentations and posters.

---

## 1. The core workflow: master versus output

The biggest mistake is to work backwards from a single flattened image. Instead, maintain a clear line of derivation from the original data to each final deliverable.

```text
Original data and files
Raw micrographs, image sequences, experimental data and plotting scripts
                          |
                          v
Editable master
Inkscape SVG, Illustrator file, vector PDF workspace,
or high-quality raster master as appropriate
                          |
          +---------------+---------------+
          |               |               |
          v               v               v
     Paper output    Presentation     Poster output
```

A single master figure can legitimately produce several purpose-built outputs:

- `figure03_master.svg` — editable vector master with layers intact;
- `figure03_paper.pdf` — vector/raster hybrid for journal submission;
- `figure03_paper_600dpi.png` — high-resolution raster alternative where required;
- `figure03_presentation.png` — appropriately sized output for a slide;
- `figure03_poster.pdf` — output prepared for large-format printing.

These are not redundant copies. They are controlled outputs designed for different purposes.

---

## 2. Vector and raster images: choosing the right foundation

The first decision is whether the information is naturally vector or raster. This determines how it should be preserved, edited and exported.

### Vector graphics
Vector graphics describe lines, curves, shapes and text mathematically. They can be scaled without losing resolution.
They are best suited to:
- graphs and plots;
- diagrams and schematics;
- annotations;
- line drawings;
- text and symbols.

Typical vector formats include SVG, EPS and vector PDF (careful PDF files are usually containers and can contain a big raster image). Where practical, retain these elements as vectors in the master figure.

### Raster or bitmap images
Raster images consist of a fixed grid of pixels. They are necessary for:
- photographs;
- micrographs;
- EBSD maps;
- DIC and strain maps;
- tomography images and slices;
- other spatially sampled measurements.

Their available detail is ultimately limited by their pixel dimensions. Typical raster formats include TIFF, PNG and JPEG.

> **Crucial warning:** Placing a raster image inside a PDF does not convert it into a vector image. The pixels remain pixels.

### Compression of raster images

#### Uncompressed
Pixel values are stored without compression. This retains the data but can produce very large files. Examples are BMP files and usually TIFF files (not always, see below). These are essential for image analysis, but have file sizes that are larger than needed for presentation purposes.

#### Lossless compression
Lossless compression reduces file size while reconstructing exactly the same pixel values. PNG is the most familiar example.
It is particularly suitable for:
- scientific maps;
- plots and diagrams;
- screenshots;
- text;
- images containing sharp lines or colour boundaries.

#### Lossy compression
Lossy compression discards information to achieve much smaller files. JPEG is the most familiar example.
JPEG can be entirely appropriate for photographs and many micrographs when small pixel-level changes are acceptable. It is usually a poor choice for plots, text, segmentation maps, EBSD maps and similar images containing sharp boundaries because compression artefacts can become visible and the original pixel values are not preserved exactly.

> **TIFF is a container, not a compression method.** A TIFF file may contain uncompressed, losslessly compressed or, in some cases, lossily compressed image data, depending on how it was written.

---

## 3. Pixels, resolution and physical size

Pixel dimensions, physical dimensions and resolution are related, but they are not the same thing.

- **Pixel dimensions:** for example, `3000 × 2000 pixels`.
- **Physical dimensions:** for example, `100 mm wide` when printed.
- **Resolution:** the number of pixels per unit length, normally expressed as pixels per inch (ppi), although publication instructions commonly use dpi.

The required pixel width can be estimated using:

$$
\text{pixels required} = \text{size in inches} \times \text{required resolution}
$$

### Worked example

A figure will be printed at 150 mm width and requires 300 ppi.

1. Convert the width to inches:

   $$150 / 25.4 \approx 5.91\text{ inches}$$

2. Multiply by the required resolution:

   $$5.91 \times 300 \approx 1770\text{ pixels}$$

The figure therefore needs to be approximately **1770 pixels wide**. This is why screenshots often produce acceptable figures for papers and presentations, depending on how the image is being rendered when the screen shot is taken.

> **Changing the DPI number in a file's metadata is not the same as resampling the image.** Changing a metadata value from 72 dpi to 300 dpi does not create additional pixels or scientific information.

Resampling changes the number of pixels. Upsampling can create a larger pixel grid, but it cannot recreate detail that was never captured.

---

## 4. Match the output to its destination
### Presentations
Think primarily in pixels because the output is a screen. A 1920 × 1080 presentation cannot display the full detail of a 6000 × 4000 pixel image occupying one small part of a slide.

Prepare an appropriately sized PNG or JPEG before inserting it. This keeps the presentation responsive, pleasant to edit and present, and easy to share without enormous attachments or slow cloud synchronisation.

> **Resizing an image on a slide is not the same as resampling it.** Dragging the handles makes the image occupy less space on the slide, but may leave every original pixel embedded in the presentation.

### Papers and PDFs
Work backwards from the final printed dimensions.
For example:

- 90 mm wide at 300 ppi requires approximately **1060 pixels**;
- 180 mm wide at 300 ppi requires approximately **2130 pixels**.

Line drawings and fine features may require greater raster resolution. Better still, retain plots, text and other graphical elements as vectors where the publication workflow supports them.

### Theses and long reports
Use images sized for their final page width rather than inserting full-resolution microscope exports. The aim is not to reduce everything indiscriminately. Preserve the original data and master images separately, while using appropriately prepared outputs in the working thesis document. Use the size guidance for papers and PDFs above.

### Posters
Work from the actual printed dimensions **and the expected viewing distance**. A poster does not automatically require enormous pixel counts merely because the paper is large.
Because posters are normally viewed from further away than papers, photographic elements often do not require 300 DPI at their final printed size. 150 DPI is usually good enough. Fine text, line drawings and small details may require more care, so inspect the exported poster PDF at an appropriate scale before printing.

---

## 5. What Word and PowerPoint do behind your back
Word and PowerPoint may:
- retain the complete high-resolution source image;
- resample an image;
- compress it;
- crop it visually while retaining the hidden pixels;
- behave differently depending on settings, export method and software version.

This creates two opposite problems.
### Problem 1: bloated files
Shrinking a large image with the mouse changes its visible size but does not necessarily remove the underlying pixels. A presentation can consequently become hundreds of megabytes without displaying any additional useful detail. Such files become slow to open, save, edit and synchronise. They are unpleasant to work with and difficult to share. The same accumulation of oversized images can make a thesis document unstable or too large for normal email attachment limits.

### Problem 2: uncontrolled degradation
MS Office may subsequently compress or resample the image, potentially softening text, introducing artefacts or removing scientifically important detail.

#### Problem 3: incompatibility
Different versions of word, different word previewers and even the same version of word but on different operating systems all handle these conversions differently. For example, if you insert a vector format image in word for mac it creates two raster copies of the same image (one for displaying on Macs one for displaying on PCs), keeps them all on file, and then shows you the one it thinks is appropriate depending on which machine you are using to view the presentation. This often doesn't work well.

### The practical solution
Resize, crop and, where appropriate, resample images before inserting them into an Office document. Prepare the version required for the destination rather than relying on Word or PowerPoint to make the decision. A well-prepared presentation should open quickly, respond immediately while slides are edited and be straightforward to share through email, Teams, OneDrive or SharePoint. A well-prepared presentation should remain usable in Word and export to a PDF that can be readily circulated.

---

## 6. Composite figures, software tools and interoperability

### Keep master figures editable
Do not assemble multi-panel publication figures in Word. Powerpoint is better but gives you poor control over resolution of individual elements. Use dedicated graphics software such as:
- [Inkscape](https://inkscape.org/);
- Adobe Illustrator.

A composite scientific figure may contain:
- vector graphs;
- bitmap micrographs;
- PNG orientation or strain maps;
- vector text;
- arrows and annotations;
- scale bars;
- panel labels.

Inkscape or Illustrator can retain vector elements as vectors while maintaining control over the resolution of individual bitmap elements. Save the complete assembly as an editable master, then export the required delivery format.

### Raster editing and resampling
Software such as GIMP provides control over:
- cropping;
- colour and contrast adjustments;
- image dimensions;
- pixel resampling;
- raster export settings.
Any scientific image adjustment should be documented and applied consistently. Never make changes that obscure, remove or misrepresent the underlying observations.

### Batch processing with ImageMagick
ImageMagick can automate repetitive operations across large image sets, including:
- format conversion;
- downsampling;
- cropping;
- removing unnecessary metadata;
- generating presentation-sized copies.
Automation is especially valuable when every output must be produced using the same operation rather than adjusted manually one file at a time.

### Interoperability
Keep plots, labels and diagrams as vectors for as long as practical, but do not assume that every program or submission portal will handle every vector format correctly.
Support can vary between:
- PowerPoint and Word;
- PDF workflows;
- graphics packages;
- journal submission systems;
- different computers and software versions.

Distinguish between:
- **Master format:** editable and preferably vector where appropriate;
- **Delivery format:** whatever works reliably for the destination.

If a vector graphic must be rasterised, do it deliberately at the required pixel dimensions. PNG is usually preferable to JPEG for graphs, diagrams and text because its lossless compression preserves sharp lines and colour boundaries.

---

## 7. Animations and video
An animated GIF is a sequence of raster images. The same considerations therefore apply to every frame:
- pixel dimensions;
- compression;
- frame rate;
- file size.

There is little value in producing an enormous GIF from source frames far larger than the presentation can display. GIF support and playback may also be inconsistent. For presentations, an MP4 video is often a better delivery format. It can normally be:
- paused at a selected frame;
- moved forwards or backwards;
- replayed from a chosen point;
- scrubbed through interactively;
- presented more efficiently than a large GIF.

FFmpeg, and graphical applications built around it, can convert image sequences or GIFs into video while controlling resolution, frame rate and compression.

> **Image sequence = master. Presentation movie = output.**

---

## Six rules to remember

1. **Keep your original data**, including raw microscope outputs, image sequences, experimental data and plotting scripts.
2. **Keep an editable master of important figures**, such as a layered SVG, Inkscape or Illustrator file.
3. **Keep graphical material as vector for as long as practical.**
4. **Control rasterisation and resolution yourself** using appropriate tools rather than leaving the decisions to Word or PowerPoint.
5. **Choose image dimensions and compression for the final destination.**
6. **Generate separate versions for papers, presentations, theses and posters** so that each document remains responsive, portable and easy to share.

---

## The payoff

The payoff is mundane but important. Your PowerPoint files remain small, responsive and pleasant to work with. Your thesis does not become a multi-gigabyte Word document that takes minutes to save or crashes during editing. PDFs remain small enough to email to supervisors and collaborators. Figures survive submission systems without unpleasant surprises. Because the original data and editable masters still exist, none of this convenience comes at the expense of the underlying scientific information.

And these days, to put this advice into action you can just give your favourite LLM this document and ask it for a script to convert your images into an appropriate format. It's that easy!
