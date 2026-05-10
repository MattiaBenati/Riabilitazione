# Riabilitazione

Desktop rehabilitation-oriented application developed in Java with Swing, image-based exercises, word recognition activities, and structured screen management.

![Java](https://img.shields.io/badge/Java-Programming-orange)
![Swing](https://img.shields.io/badge/GUI-Java%20Swing-blue)
![IntelliJ IDEA](https://img.shields.io/badge/IDE-IntelliJ%20IDEA-purple)
![Desktop App](https://img.shields.io/badge/Application-Desktop%20App-informational)

## Demo

https://github.com/user-attachments/assets/3829a7b1-5143-40ba-ad0c-17524ee1bccf

## What is it?

Riabilitazione is a desktop Java application designed to support image-based and word-based rehabilitation exercises.

The software allows the user to select a folder containing images and automatically generates exercises using the image file names as the words to recognize or guess.

The application provides two main exercise modes: one focused on guessing the word associated with an image, and one focused on selecting the correct image associated with a displayed word.

The project is organized into separate packages for utility methods, word modeling, and graphical screens, with each screen divided into model, view, and controller components.

## Features

- Desktop graphical user interface
- Home screen with exercise mode selection
- Folder selection through a directory chooser
- Automatic image loading from a selected folder
- Support for `.jpg`, `.jpeg`, and `.png` image files
- Automatic word generation from image file names
- Removal of unsupported characters from generated words
- Automatic lowercase conversion
- Randomized exercise order
- Image resizing and rounded-corner rendering
- Word guessing mode
- Image guessing mode
- Progress bar for exercise navigation
- Forward and backward navigation between exercises
- Reset option for restarting the activity
- Option to change the selected image folder
- Custom application icon
- Structured Java package organization

## Key Technical Aspects

- Java Swing-based desktop interface
- Screen organization based on model, view, and controller components
- Directory scanning for supported image formats
- Automatic conversion of image file names into exercise words
- Input normalization and character filtering
- Randomized word and image order using shuffled lists
- Builder pattern used to create word exercise objects
- Singleton pattern used for directory selection management
- Image processing for resizing and rounded visual rendering
- Difficulty management for word guessing exercises
- Progress tracking through `JProgressBar`
- Separation between utility methods, word data structures, and screen logic
- IntelliJ IDEA GUI Designer `.form` files used for interface layout

## Technology Stack

- Java
- Java Swing
- AWT
- ImageIO
- IntelliJ IDEA GUI Designer
- IntelliJ IDEA or another Java-compatible IDE

## Requirements

- Java JDK 11 or later
- IntelliJ IDEA recommended
- Windows, macOS, or Linux with Java support
- A folder containing image files in `.jpg`, `.jpeg`, or `.png` format

The project uses IntelliJ IDEA GUI Designer `.form` files, so opening and running the project with IntelliJ IDEA is recommended.

## Quick Start

### Clone the repository

```bash
git clone https://github.com/MattiaBenati/Riabilitazione.git
cd Riabilitazione
```

### Open the project

Open the project folder with IntelliJ IDEA.

Make sure the project SDK is set to Java 11 or later.

### Run the application

Run the `Main.java` file from the IDE.

The application starts from the home screen and allows the user to choose one of the available exercise modes.

## Usage

1. Start the application
2. Choose one of the available exercise modes from the home screen
3. Select a folder containing supported image files
4. The software reads the images and generates the related words from the file names
5. Complete the exercise using the selected mode
6. Navigate through the exercises using the available controls
7. Reset the activity or select a different folder when needed
8. Return to the home screen using the home button

## Exercise Modes

### Guess the Word

In this mode, the application displays an image and asks the user to guess the related word.

The word is generated from the image file name and displayed with hidden or partially revealed characters depending on the selected difficulty.

The user can type a full word attempt or gradually reveal letters through correct input.

### Guess the Image

In this mode, the application displays a word and several image options.

The user must select the image that correctly matches the displayed word.

Correct and incorrect choices are visually highlighted, and the user can move through the exercise list after completing each item.

## Controls

| Control | Action |
| --- | --- |
| `Indovina Parola` | Start the word guessing exercise |
| `Indovina Immagine` | Start the image guessing exercise |
| `Cartella` | Select a different image folder |
| `Reset` | Restart the current activity |
| `Home` | Return to the home screen |
| `Avanti` | Move to the next exercise |
| `Indietro` | Move to the previous exercise |
| `Facile` | Use the easiest word guessing level |
| `Medio` | Use the intermediate word guessing level |
| `Difficile` | Use the hardest word guessing level |
| `Attive` | Enable vowel-based symbol visualization |
| `Disattivate` | Disable vowel-based symbol visualization |

## Project Structure

```text
Riabilitazione/
├── Main.java
├── metodi/
│   ├── Caratteri.java
│   ├── Costanti.java
│   ├── Directory.java
│   └── Immagini.java
├── parola/
│   ├── Parola.java
│   └── ParolaBuilder.java
├── risorse/
│   ├── icona.png
│   └── sfondo.png
└── schermata/
    ├── home/
    │   ├── HomeController.java
    │   ├── HomeModel.java
    │   ├── HomeView.form
    │   └── HomeView.java
    ├── indovinaimmagine/
    │   ├── IndovinaImmagineController.java
    │   ├── IndovinaImmagineModel.java
    │   ├── IndovinaImmagineView.form
    │   └── IndovinaImmagineView.java
    └── indovinaparola/
        ├── IndovinaParolaController.java
        ├── IndovinaParolaModel.java
        ├── IndovinaParolaView.form
        └── IndovinaParolaView.java
```

## Architecture Overview

The project follows a structured Java organization, separating utility logic, word data management, and graphical screen components.

- `Main.java`: starts the application, sets the Windows Swing look and feel, and opens the home screen
- `metodi/Caratteri.java`: manages word normalization, character filtering, lowercase conversion, symbol generation, and letter updates
- `metodi/Costanti.java`: stores shared constants, supported formats, application title, icon, and home image resources
- `metodi/Directory.java`: manages folder selection and reads supported image files from the selected directory
- `metodi/Immagini.java`: manages image resizing, rendering, and rounded-corner formatting
- `parola/Parola.java`: represents an exercise word with its related image, difficulty, visible letters, and symbol state
- `parola/ParolaBuilder.java`: builds `Parola` objects from image files and initializes word-related data
- `schermata/home/`: contains the home screen model, view, and controller
- `schermata/indovinaparola/`: contains the word guessing screen model, view, and controller
- `schermata/indovinaimmagine/`: contains the image guessing screen model, view, and controller
- `risorse/`: contains graphical resources used by the application

## Output

The software displays a graphical desktop interface built with Java Swing.

During execution, it shows the home screen, image-based exercises, word-based exercises, selectable options, progress tracking, difficulty controls, navigation buttons, and visual feedback for correct or incorrect answers.

The application does not generate external output files; it processes the selected image folder and displays the rehabilitation exercises directly through the graphical interface.
