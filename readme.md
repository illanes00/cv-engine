## Dynamic Multi-Language CV in LaTeX

### Overview

This project is a dynamic and modern CV template created using LaTeX, which allows you to generate a formal CV with ease. The CV content is managed through JSON files, making it highly flexible and easily customizable. With this setup, you can quickly switch between different languages, including English, Spanish, French, and Latvian, without modifying the core LaTeX structure.

### Features

- **Dynamic Content Management**: All sections of the CV, such as education, work experience, and publications, are stored in JSON files. This makes it easy to update and maintain the CV without directly editing the LaTeX code.
  
- **Multi-Language Support**: The template supports multiple languages (English, Spanish, French, and Latvian). You can switch the language of the entire document with a single change in the configuration file.
  
- **Modern and Formal Design**: The CV is designed to be clean, professional, and modern, ensuring that it makes a strong impression.
  
- **Section Customization**: Easily include or exclude sections based on the type of CV you want to generate (e.g., full CV or a shorter resumé).

### File Structure

- **`main.tex`**: The main LaTeX file that compiles the CV. It includes the necessary packages and inputs the various components of the CV.

- **`styles.tex`**: Contains the styling and formatting for the CV, such as fonts, colors, and spacing.

- **`config.tex`**: Configuration file where you set the language (`cvLang`) and version (`cvVersion`) of the CV (e.g., full CV or resumé).

- **`translations.tex`**: Stores the translations for section titles and other key terms in different languages.

- **`00_header.tex`**: Defines the header of the CV, including personal information like name and contact details.

- **`00_languageselector.tex`**: Determines the language of the document based on the `cvLang` variable set in `config.tex`.

- **`01_education.tex`**: Handles the Education section, dynamically loading content from the corresponding JSON file.

- **`02_experience.tex`**: Manages the Work Experience section, with content sourced from JSON.

- **`09_publications.tex`**: Displays the Publications section, again pulling data from JSON.

- **`11_additional_info.tex`**: Additional information section, customizable through JSON.

- **`<section>.json`**: JSON files that contain the content for each section of the CV.

### How to Use

1. **Set Up the Environment**: Ensure you have a LaTeX distribution installed that supports LuaLaTeX, as well as any required packages (e.g., `fontspec`, `luacode`, `hyperref`, etc.).

2. **Edit the JSON Files**: Customize the content of your CV by editing the relevant JSON files. Each JSON file corresponds to a section in the CV.

3. **Configure the CV**:
   - Open `config.tex`.
   - Set `\cvLang` to the desired language (`en`, `es`, `fr`, or `lv`).
   - Set `\cvVersion` to either `extenso` for a full CV or `resume` for a shorter version.

4. **Compile the CV**: Run `main.tex` through a LaTeX editor or command line using LuaLaTeX. This will generate the PDF of your CV.

5. **Switching Languages**: To switch languages, simply change the `\cvLang` variable in `config.tex` and recompile the document.

### Example

To generate a CV in English with a full version:

```latex
% In config.tex
\newcommand{\cvLang}{en}   % Set language to English
\newcommand{\cvVersion}{extenso}  % Full CV version
```

To switch to a shorter resumé in Spanish:

```latex
% In config.tex
\newcommand{\cvLang}{es}   % Set language to Spanish
\newcommand{\cvVersion}{resume}  % Shorter resumé version
```

### Contributing

If you have suggestions or improvements, feel free to submit a pull request or open an issue.

### License

This project is open-source and available under the [MIT License](LICENSE).

### Acknowledgments

Thanks to the LaTeX and LuaLaTeX communities for their incredible tools and resources that made this project possible.