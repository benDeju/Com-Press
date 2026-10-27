# Com-Press

**Com-Press is a Windows desktop utility for compressing and converting files through a category-based radial action wheel.** It brings common file tasks together in one place, so you can choose a task by category instead of configuring a separate menu for every format.

## What Com-Press does

Select one or more files (or folders for archive creation), open the Com-Press wheel, choose a category, and then choose an action. Com-Press processes the selected items locally and shows task progress and the result in the app.

The wheel groups actions into five categories:

### Compress

- Create ZIP, 7Z, TAR, TAR.GZ, and GZIP archives.
- Extract supported ZIP and TAR archives.
- Compress multiple selected files and folders into a single archive. Multiple selections use the name `Multiple Compress`.
- Choose an archive compression level in Preferences. Higher levels may take longer and can produce smaller archives, depending on the files.

ZIP, TAR, TAR.GZ, and GZIP use Python's bundled standard library. Creating 7Z archives requires 7-Zip to be installed on the computer.

### Documents

- Combine one or more pictures into a multi-page PDF.
- Convert Word documents to PDF.
- Convert PDF files to editable Word documents.
- Export PDF pages as PNG or JPG images.
- Unlock a PDF when you provide its current password. Com-Press does not bypass unknown passwords.

Microsoft Word or LibreOffice is recommended for better Word-to-PDF formatting. If neither is available, Com-Press can use a basic text-and-table fallback for DOCX files.

### Pictures

Convert supported picture files to PNG, JPG, GIF, WEBP, ICO, HEIC, AVIF, TIFF, BMP, TGA, JPEG 2000, PPM, or PCX. The exact result depends on the features supported by the source and target formats; for example, some formats do not preserve animation or transparency.

### Audio

Convert supported audio files to MP3, WAV, AAC, M4A, FLAC, OGG, WMA, OPUS, or AIFF. The audio category can also use a video file as the source when extracting or converting its audio track.

### Video

Convert supported videos to MP4, MOV, MKV, WEBM, AVI, WMV, MPEG, or FLV. The category also includes an action to extract a video's audio as MP3.

## Using the radial wheel

The wheel opens at the pointer. Select a category to see its actions; use the center Back control to return to the previous wheel. The category layout is ready to use without setting up individual buttons.

The wheel can be opened from the app's wheel preview, with its keyboard shortcut, or—when enabled—from a selected file in File Explorer or on the desktop by holding the left mouse button. The hold gesture is optional and can be turned on in **Preferences**. After the wheel appears, choose the category and action for the selected item.

## Preferences and app behavior

Preferences let you adjust:

- Light, dark, or system color theme.
- Default archive compression level and save folder.
- Wheel keyboard shortcut and size.
- Optional File Explorer and desktop hold gesture.
- Starting with Windows and starting minimized in the system tray.
- Minimizing the app to the system tray.

Com-Press keeps task output beside the source files by default unless a different archive destination is configured. It avoids overwriting existing outputs by choosing a unique filename. Media conversions run without opening a command window, and longer jobs display progress in the app.

## Offline use

Com-Press performs its compression and conversion work locally and does not require an internet connection for normal use. The packaged application includes its Python conversion libraries and FFmpeg. Some optional operations need a separate local program:

- **7Z archive creation:** 7-Zip.
- **Full-fidelity Word-to-PDF conversion:** Microsoft Word or LibreOffice is recommended.

## System requirements

- Windows 10 or Windows 11, 64-bit.
- 4 GB RAM minimum; 8 GB recommended for large media files.
- Approximately 2 GB free disk space for the application and conversion tools, plus space for output files.
- Microsoft Word or LibreOffice recommended for full-fidelity Word-to-PDF conversion.
- 7-Zip required only for creating 7Z archives.

## Author

Created by **Benedict Leoveras**.
