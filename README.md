# zip-to-text

A simple Python script which takes your .zip file (e.g. a zipped version of your codebase) and converts it into a flat, single text file which can then be used for things like discussing your code with LLMs.

# How to use

1. Make a copy of your codebase and compress it into a .zip file
2. Update the `zip_path` variable to point to your .zip file
3. Update the `output_file` variable to point to where you want the text file to be generated
4. Run the script with the command `python flatten-text.py`

A text file with your flattened codebase will then be generated, complete with file names and dividers between each file.

# Example output

```
---------
File: mod_form.php

<?php

defined('INTERNAL') || die;

require_once($CFG->dirroot.'/course/form_mod.php');

class mod_form extends form_mod {

    function definition() {

        $mform = $this->_form;

        // Add a field for the template ID
        $mform->addElement('text', 'templateid', get_string('templateid', 'mod_verifyed'));
        $mform->setType('templateid', PARAM_INT);
        $mform->addRule('templateid', null, 'required', null, 'client');

        // Add standard course module elements
        $this->standard_coursemodule_elements();

        // Add standard buttons, common to all modules
        $this->add_action_buttons();
    }
}

---------
File: version.php

<?php

$plugin->component = 'mod_plugin';
$plugin->maturity = MATURITY_STABLE;
$plugin->release = 'v1.0.0';

---------
File: lib.php

<?php

etc...
```
