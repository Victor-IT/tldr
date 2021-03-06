# tomb

> Manage encrypted storage folders that can be safely transported and hidden in a filesystem.

- Create a new tomb with an initial size of 100MB:

`tomb dig -s {{100}} {{encrypted_folder.tomb}}`

- Create a new key file that can be used to lock a tomb; user will be prompted for a password for the key:

`tomb forge {{encrypted_folder.tomb.key}}`

- Initialize and lock an empty tomb using a key made with `forge`:

`tomb lock {{encrypted_folder.tomb}} -k {{encrypted_folder.tomb.key}}`

- Mount a tomb (by default in /media) using its key, making it usable as a regular filesystem folder:

`tomb open {{encrypted_folder.tomb}} -k {{encrypted_folder.tomb.key}}`

- Close a tomb (fails if the tomb is being used by a process):

`tomb close {{encrypted_folder.tomb}}`

- Forcefully close all open tombs, killing any applications using them:

`tomb slam all`

- List all open tombs:

`tomb list`
