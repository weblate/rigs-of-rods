Basically these steps are required to get up to date translations:
- dev only: Extract \*.pot template from code, upload to Weblate (see below)
- wait for community to translate
- compile \<lang.mo\> for these translations (see below)
- put \<lang\>.mo in ```bin/languages/```

### Update source file on Weblate
The source file (\*.pot) on Weblate serves as the base for all translations and
should be updated whenever new strings which need translation have been added to the source.

```bash
# Extract new translations template
cmake -P extract_pot.cmake
# Commit the languages/ror.pot file and it will be automatically updated by Weblate
```

### Compile *.mo files from Weblate
A \*.mo file is a translation for a given language in binary form.  
Rigs of Rods needs \*.mo files for the translations to appear ingame.

```bash
# Compiles *.mo files for all languages where translations are available
cmake -P compile_mo.cmake
```
