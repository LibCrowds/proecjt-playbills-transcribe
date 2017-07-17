# project-playbills-transcribe

Playbills transcription projects for LibCrowds, designed for use with the 
[libcrowds-bs4-pybossa-theme](https://github.com/LibCrowds/libcrowds-bs4-pybossa-theme).

**:warning: DEPRECATED: Replaced by [project-iiif-annotate](https://github.com/LibCrowds/project-iiif-annotate)**

## Creating a new project

Install and configure [pbs](https://github.com/Scifabric/pbs).

Choose a set of tasks from [tasks.json](tasks/tasks.json) (e.g. `"performances"`) 
and a JSON file where the info field contains the keys *aleph_sys_no*, *image_ark* 
and *regions*. A new task will be created for each permutation of an image, 
each region now associated with that image and each task in the chosen task set.

To generate a new project using the inputs provided above and push it to the server 
install and configure [pbs](https://github.com/Scifabric/pbs), then:

```
python generate_project.py <task set> <path to json file>
cd gen
pbs create_project
pbs add_tasks --tasks-file=tasks.csv
pbs update-task-redundancy --redundancy 3
pbs update_project
```

Visit the project settings page and update the category, webhook and 
thumbnail. The project is now ready to be published.
