# Fossil XToFu - C

Fossil Standard Component Libraries (FSCL) by Fossil Logic represent the pinnacle of software development, embodying our commitment to quality, security, and practicality. These meticulously curated libraries serve as the cornerstone for crafting cutting-edge applications, offering a foundation built on excellence in code. With FSCL, Fossil Logic empowers developers to seamlessly integrate standardized components that elevate the overall performance and reliability of digital solutions, setting a new standard for software excellence.

Fossil XTofu serves as the foundational generic type for creating generic algorithms and data structures. This versatile library provides essential secure type checking, streamlining the development process and ensuring a solid framework for your flavorless applications.

## Who is This For?

This guide is designed for developers of all skill levels who want to use the Meson build system for their projects. It assumes basic familiarity with command-line interfaces and project organization.

## Prerequisites

Before getting started, make sure you have the following installed:

- **Meson Build System**: This project relies on Meson. If you don't have Meson installed, visit the official [Meson website](https://mesonbuild.com/Getting-meson.html) for installation instructions.

## Setting up Meson Build

1. **Install Meson**:
   - Follow the installation instructions on the [Meson website](https://mesonbuild.com/Getting-meson.html) for your operating system.

## Setting up, Compiling, Installing, and Running the Project

1. **Create a Wrap File**:

Create a directory named subprojects in the root directory, next create a file named `tscl-xtofu-c.wrap` in the `subprojects` directory of your project with the following content:

   ```bash
   # ================ #
   #  FSCL Wrap File. #
   # ================ #
   [wrap-git]
   url = https://github.com/fossil-lib/fscl-xtofu-c.git
   revision = main
   
   [provide]
   fscl-xtofu-c = fscl_xtofu_c_dep
   ```

2. **Integrate Wrap File in Meson Build**:
   ```meson
   project('my_project', 'c',
       version : '0.1',
       default_options : ['warning_level=3'])

   exe = executable('my_project', 'my_project.c',
       dependencies : dependency('fscl-xtofu-c'), # add this line
       install : true)

   test('basic', exe)
   ```

3. **Compile the Project**:
   ```bash
   meson setup builddir
   meson compile -C builddir
   ```

## Including the Demo and Running Tests

To run tests, you can use the following options when configuring the build:

- **Running Tests**: Add `-Dwith_test=enabled` when configuring the build.

Example:

```bash
meson setup builddir -Dwith_test=enabled
```

## Contributing

If you're interested in contributing to this project, please consider opening pull requests or creating issues on the [GitHub repository](https://github.com/fossil-lib/fscl-xtofu-c).

## Feedback and Support

If you encounter any issues, have questions, or would like to provide feedback, don't hesitate to open an issue on the [GitHub repository](https://github.com/fossil-lib/fscl-xtofu-c/issues).

## License

This project is licensed under the [Mozilla Public License](LICENSE).

---

Thank you for choosing this project with the Meson build system. Happy coding and building amazing projects!
