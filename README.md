# Ansible Collection - jerabekjiri.ansible_patterns

## Specifications:
    - A pattern MUST be contained within a single directory in the /extensions/patterns/ directory of an Ansible collection.
    - An Ansible pattern directory name MUST contain only <specify character requirements>
    An Ansible collection MAY contain zero or more patterns.


### Required files

####  meta/pattern.json
    - A pattern MUST include exactly one meta file defining the pattern metadata and AAP resources it requires.
    - The pattern definition meta file MUST be a valid instance of the Ansible pattern schema.

#### README.md
    - A pattern MUST include a README file.

#### playbooks/
    - A pattern MUST contain a playbooks/ directory.
    - The playbooks directory MUST contain at least one playbook.
    - A pattern MAY contain multiple playbooks. 
        - If a pattern contains multiple playbooks, it MUST define a primary playbook in its setup file.
    - All required and optional input variables to a pattern playbook MUST be defined in a play argument spec following the documented play argument spec format (draft).
    - If a pattern playbook requires any user-provided information other than variables to launch as a job template, such as inventory or credentials, those MUST be specified as fields_required_at_launch in the relevant controller_job_templates section of the pattern definition meta file.

#### execution_environments/
    - A pattern MAY contain an executions_environments/ directory.
    - If included, the execution_environments/ directory MUST contain exactly one execution environment definition file following the documented format.
    - The execution environment definition file MUST include all dependencies needed to execute the pattern automation(s). This includes system, Python, and Ansible collection dependencies.


### Optional files

#### templates/
    - A pattern MAY contain a templates/ directory to hold templates specific to catalogs that may publish the pattern, such as Red Hat Developer Hub or ServiceNow.
    - The templates directory MAY contain one or more catalog template files.


### Other requirements
    - A pattern MUST inherit the version number of the collection that contains it.
    - A pattern MUST be valid according to the requirements specified in this document, including validation of each file contained in the pattern against its relevant schema.
    - How/where is testing represented? Do we require any amount of testing of a pattern or just validation that the pattern meets the spec?

