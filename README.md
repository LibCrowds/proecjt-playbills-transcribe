# project-playbills-transcribe

Playbills transcription projects for LibCrowds, designed for use with the 
[libcrowds-bs4-pybossa-theme](https://github.com/LibCrowds/libcrowds-bs4-pybossa-theme).


## Creating a new project

Install and configure [pbs](https://github.com/Scifabric/pbs).

Choose a set of tasks from [tasks.json](tasks/tasks.json) (e.g. `"actors"`) 
and the project ID of a completed 
[project-playbills-mark](https://github.com/LibCrowds/project-playbills-mark) 
project.

To generate a new project using the inputs provided above and push it to the server:

```
python generate_project.py <task set> <project ID>
cd /gen
pbs create_project
pbs update-task-redundancy --redundancy 3
pbs update_project
```

The project can now be published from the project settings page.