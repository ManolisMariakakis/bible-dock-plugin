# Bible Dock Plugin
Free Bible dock plugin for OBS Studio

## Summary

The **Bible Dock Plugin** is a free and customizable tool designed for use with OBS Studio. It allows users to seamlessly integrate Bible text, chapter navigation, and verse selection into their live streams or presentations. The plugin offers a variety of features that enhance the display and control of Bible verses during presentations, making it suitable for both full-screen and partial display views.

The plugin consists of several components:

- **Browser Source Pages**: These include the chapter and verse pages, which provide a user-friendly interface for displaying and navigating Bible chapters and verses within OBS. The pages are styled using customizable dock pages that define the look and feel of the text and layout.

- **Dock Pages**: These pages enable users to select books, chapters, and specific verse ranges for display, navigating Bible chapters and verses within OBS. They also provide options to set up browser source parameters and manage references.

- **Bible Data Integration**: The plugin utilizes CSV files to store and retrieve Bible texts, versions, and book details. The folder [zefaniaXML2CSV](https://github.com/ManolisMariakakis/Zefania-Bibles-XML2CSV-Preservation/tree/main/zefaniaXML2CSV) contains Bible texts in multiple versions and languages, ensuring compatibility. Additionally, users can generate Bible text files using external tools like `theWord.net`.

This plugin is particularly beneficial for live-streaming Bible readings, sermons, or study sessions, providing smooth control over the presentation of scripture, making it an invaluable tool for religious speakers.

## Compatibility

The **Bible Dock Plugin** is designed to work seamlessly with the latest version of OBS Studio on multiple operating systems, including Windows, macOS, and Linux. The plugin is compatible with various Bible versions formatted in CSV files, enabling users to integrate a wide range of Bible text. Users are encouraged to ensure that their CSV files adhere to the required structure for optimal performance. Additionally, the plugin works best with modern web browsers that support HTML5, ensuring that the browser sources render correctly in the OBS environment.

A web server is required to run the HTML pages, ensuring that they are properly served and accessible within the OBS environment.


## Installation

Follow these steps to install the **Bible Dock Plugin** for OBS Studio:

- Obtain the plugin files from [GitHub](https://github.com/ManolisMariakakis/bible-dock-plugin).
- Set up Browser Sources in OBS Studio:
  - Use the **Browser source** (`chapter.html`, `verse.html`), configure the **URL** to point to the respective HTML file.
- Dock the Bible Pages in OBS Studio:
  - Use the **Dock Pages** (`books.html`, `fromverse.html`, and `reference.html`) to point to the respective HTML file.
- Adjust the appearance (font size, colors, margins, etc.) of the Bible text, using the `chapter_variables.html` and `verse_variables.html` dock pages.
- Prepare Bible Book Names: 
  - Update the `bibletable.txt` file to include Bible book names in your desired language. Ensure the file follows the correct format with the appropriate book numbers, names, and the number of chapters for each book.
- Choose Bible Versions:
  - Bible texts compatible with various versions and languages are available in the [zefaniaXML2CSV](https://github.com/ManolisMariakakis/Zefania-Bibles-XML2CSV-Preservation/tree/main/zefaniaXML2CSV) folder.
  - You can generate new CSV files using tools like `theWord.net`
  - Ensure that the `versions.txt` file is updated accordingly.

Below is an example of how the dock pages appear in OBS:

![Dock Pages in OBS](https://github.com/ManolisMariakakis/bible-dock-plugin/blob/main/dock.png)


## The Browser Source Pages

### The Chapter Page

1. Contains the sections Title, Chapter, Footer.
2. Footer is below Chapter, and Chapter is below Title.
3. The Title is composed of the text version, the book, and the chapter number.
4. The chapter text is scrollable, with an option to select verse number, which will appear at the beginning of the scrolling window.
5. Suitable to cover all or part of the display view.
6. The name of the Browser Source page is `chapter.html`.
7. The style of the page is provided by the dock page `chapter_variables.html`.

### The Verse Page

1. Contains the sections Chapter and Title.
2. Title is below Chapter.
3. The Title is composed of the text version, the book, and the chapter number.
4. It is possible to select part of the chapter by choosing from-to verse numbers.
5. The height of the chapter area is dynamically adjusted based on the selected from-to verse numbers. Additionally, the `justify-content` property is set to `flex-end`, ensuring that the content is aligned at the bottom of the display.
6. Suitable to cover part of the display view, with or without a transparent background.
7. The name of the Browser Source page is `verse.html`.
8. The style of the page is provided by the dock page `verse_variables.html`.

## The Dock Pages

### The Book-Chapter Selection Page

1. The page contains all the chapters of all books.
2. Text version is selected from the versions list box.
3. Chapters are selected by clicking on the book-chapter number.
4. The book names displayed are sourced directly from the `bibletable.txt` file.
5. The name of the dock page is `books.html`.

### The Verse Selection Page

1. The page contains all the verse numbers of the last selected book-chapter.
2. In the Chapter browser page, the verse number that will appear at the beginning of the scrolling window is the verse number selected.
3. In the Verse browser page, the verse range that will appear is the from-to verse numbers selected.
4. The name of the dock page is `fromverse.html`.

### The References Selection Page

1. The page contains all the references selected by the Book-Chapter and Verse pages (version, book, chapter, from-verse).
2. When a reference is selected, the display is updated accordingly, showing the relevant Bible text and details based on the selected reference.
3. There is a button to clear all references and a button to delete a specific reference.
4. The name of the dock page is `reference.html`.

### The Chapter Page Setup

1. It is a dock page and does not need to be visible in OBS, as it is only used to configure the Browser Source page `chapter.html`.
2. The setup parameters are listed in the paragraph [Chapter Page Variables](#Chapter-Page-Variables).
3. The name of the dock page is `chapter_variables.html`.

### The Verse Page Setup

1. It is a dock page and does not need to be visible in OBS, as it is only used to configure the Browser Source page `verse.html`.
2. The setup parameters are listed in the paragraph [Verse Page Variables](#Verse-Page-Variables).
3. The name of the dock page is `verse_variables.html`.

### Chapter Page Variables

The `Chapter Page Variables` offers extensive customization options through CSS styling, allowing you to tailor the look and feel of Bible display to match your presentation needs.

**Generic**
- Font Family 
- Height 
- Margin Top 
- Margin Left 

**Title**
- Height 
- Background Color or Transparent
- Color 
- Padding Top 
- Padding Left 
- Padding Bottom 
- Font Size 
- Font Weight 
- Border 
- Border Color

**Chapter**
- Background Color or Transparent
- Color 
- Padding Top 
- Padding Left 
- Padding Right 
- Font Size 
- Font Weight 
- Border 
- Border Color 
- Line Height 

**Verse Number**
- Font Size 
- Font Weight 
- Background Color or Transparent
- Color 
- Padding Right

**Footer**
- Height
- Background Color or Transparent
- Border
- Border Color 

### Verse Page Variables

The `Verse Page Variables` offers extensive customization options through CSS styling, allowing you to tailor the look and feel of Bible display to match your presentation needs.

**Generic**
- Font Family 
- Width 
- Height 
- Margin Bottom 
- Margin Left

**Title**
- Height 
- Background Color or Transparent
- Color 
- Padding Top 
- Padding Left 
- Padding Bottom 
- Font Size 
- Font Weight 
- Border 
- Border Color 

**Verse**
- Background Color or Transparent
- Color 
- Padding Top 
- Padding Left 
- Padding Right 
- Font Size 
- Font Weight 
- Border 
- Border Color 
- Line Height

**Verse Number**
- Font Size 
- Font Weight 
- Background Color or Transparent
- Color
- Padding Right 

## Data

### Bible Books File

1. The name of the file is `csv/bibletable.txt`.
2. File fields description:
   - Book number
   - Book name
   - Number of chapters in that book
   - The field separator is `,`
   - Tested with file encoding UTF-8

### Bible Versions File

1. The name of the file is `csv/versions.txt`.
2. File fields description:
   - Version name
   - File name of text
   - The field separator is `,`
   - Tested with file encoding UTF-8

### Bible Texts

1. Files are stored in the folder `csv`
2. The file name must exist as a record in the Bible Versions file `csv/versions.txt`
3. File fields description:
   - Book number (matches with a record in the Bible Books file `csv/bibletable.txt`)
   - Chapter number
   - Verse number
   - Verse text (between `"`)
   - The field separator is `,`
   - Tested with file encoding UTF-8


### Available Bible Texts

Before generating Bible text files, users should note that there are already Bible texts compatible with various versions and languages available in the [zefaniaXML2CSV](https://github.com/ManolisMariakakis/Zefania-Bibles-XML2CSV-Preservation/tree/main/zefaniaXML2CSV) folder. This resource provides a convenient option for users looking for pre-formatted Bible texts that ensure compatibility with the plugin.

### Text Generator from theWord.net

`theWord.net` is a free, high-quality Bible software containing hundreds of Bible versions in many languages. You can check if your Bible version exists using the link [Download add-on modules](https://www.theword.net/index.php?downloads.modules&group_id=2&o=title&l=english).

One of the most beneficial features of **theWord** is its extensive and customizable ability to copy Bible verses.

- First, you need to change the configuration language file of the application to export the book number instead of the book name. To avoid modifying the existing configuration, copy `export.lng` to the folder where `theword.exe` is located and (after restarting the application) change the default language to `Export`. 

- Pressing F5 opens the Verse-Copy Dialog, where you can select the Bible version and all verses. Then, take care of the verse formatting:
  - At Step 1: Select all verses.
  - At Step 2: Select the text version and check the checkbox `Short book names`.
  - At Step 3: Uncheck everything.
  - At Step 4: Choose the following:
    - Predefined format: `16 Custom (user defined)`.
    - Before each verse: `%b,%c,%v,"`.
    - After each verse: `"%n`.
    - At the beginning of the chapter: Leave empty.
    - In Advanced options: Select `Copy as text only (no formatting)`.
    - Then perform a copy and paste action to a UTF-8 file.

Finally, once the exported file has been verified for accuracy, a corresponding entry should be added to the versions.txt file.

## Sample installation

To install the sample Bible Dock Plugin in OBS Studio, you can set up the following Browser Sources and Dock Pages using the provided links to the HTML files:

### Browser Sources

- **Chapter Page**: `https://ymnoi.gr/bible-dock/chapter.html`
- **Verse Page**: `https://ymnoi.gr/bible-dock/verse.html`

### Dock Pages

- **Book-Chapter Selection Page**: `https://ymnoi.gr/bible-dock/books.html`
- **Verse Selection Page**: `https://ymnoi.gr/bible-dock/fromverse.html`
- **References Selection Page**: `https://ymnoi.gr/bible-dock/reference.html`
- **Chapter Page Variables Setup**: `https://ymnoi.gr/bible-dock/chapter_variables.html`
- **Verse Page Variables Setup**: `https://ymnoi.gr/bible-dock/verse_variables.html`

Enjoy!
