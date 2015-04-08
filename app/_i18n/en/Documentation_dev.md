

* This will become a table of contents (this text will be scraped).
{:toc}

#Presentation

PLM (Product Lifecycle Management) is an area of ​​activity whose purpose is to create and maintain products throughout their life cycle, since the establishment of the specification of product and related services until the end of life. (source: Wikipedia)

PLM is a strategy that allows companies to share product data allowing all stakeholders (employees, suppliers, customers, etc...) to act collaboratively on product development.

Beyond traditional PLM functionalities, DocDokuPLM offers to view and collaborate on a digital model (Catia, Inventor, AutoCAD, STEP, IFC, COLLADA, OBJ, etc...) on all kind of terminals (PC, Mac, Linux, Tablet, Smartphone) directly in the browser without any installation or plugins.

In addition, DocDokuPLM proposes advanced functions such as fine grained access right management, document templates or out of the box BPM (Business Process Management) through a graphical workflow editor.

DocDokuPLM is a user friendly, ergonomic tool.

DocDokuPLM User Guide describes and explains how to use the software. It is a comprehensive manual useful for any end users.

#User Management

To be able to log into the application, everyone needs an account identified by a login and protected by a password.

Each user which hence represents an actor of the system holds specific access rights for every workspace he belongs to. Users can also participate in business processes.

##User creation

To create an account, click on the link “sign up!” from the home page.

{% image /assets/images/documentation/en/register.png "Registration link"%}

The first step is thus to register. All fields are required.

{% image /assets/images/documentation/dev/en/register2.png "Creating a User"%}

##User edition

{% image /assets/images/documentation/dev/en/settings.png "Account Management"%}

Subsequently all settings can be changed, except the User ID which is immutable.

The account edition page is accessible on the "My account" submenu which also allows to reset the password. The time zone is used to display times.

{% image /assets/images/documentation/dev/en/edition.png "Account Edition"%}

#Workspace Management

##Workspace creation

Once your account created, you can instantiate new workspaces.

{% image /assets/images/documentation/en/creation.png "Workspace creation"%}

Workspace is the top level context object that gathers documents, parts, business processes and products. The initial workspace administrator is the user who created it.

The "freeze folder structure except for workspace manager" option must be checked if you do not want other users to modify the directory structure.

##Workspace settings

To edit the workspace properties, click on "Workspaces administration".

{% image /assets/images/documentation/dev/en/settings.png "Account Management"%}

Then, select the workspace you want to edit.

{% image /assets/images/documentation/en/workspace.png "Manage your workspaces"%}

You manage workspaces access at user level or by creating groups.
Access rights administration is discussed in the next chapter.

###Dashboard

The dashboard provides statistics on your workspace (disk space, number of documents and parts, checkin/checkout per user, etc..).

{% image /assets/images/documentation/en/dashboard.png "Airplane-T01 workspace dashboard"%}

##Collaborative messaging

All users of the same workspace can communicate in real-time with our built-in communication module.
This module offers the ability to engage an instant messaging conversation or a video conference on the fly. Hence, users can easily exchange parts and documents and thus speed up the process of product development.

The co-workers menu lists the current connected users (green) and others. A click on the camera icon will start a video conversation.

{% image /assets/images/documentation/en/coworkers.png "Co-workers menu"%}

{% image /assets/images/documentation/en/videochat.png "Video chat invitation"%}

In addition to the co-workers menu, whenever a user name appears in blue inside the application, a simple click brings up a contextual menu. A conversation started this way carries out the context to the recipient user so he is informed of what is probably the subject of the communication (document, part).

{% image /assets/images/documentation/dev/en/conversation.png "Co-worker contextual conversation menu"%}

#Access right controls

##Workspace access rights

###User access management

Workspace administrator defines permissions to users which can be either full or read-only access.

It’s also possible to disable users which has the effect to forbid them to log in.

{% image /assets/images/documentation/en/user_management.png "Workspace Users Management"%}

Furthermore, users can be assigned into groups holding the permissions.

A full access user can:

* Create, modify or delete documents and parts
* Modify the folder structure (if not restricted to administrator)
* Move documents in folders
* Checkin/Checkout documents and parts

A read-only user can:

* View documents and parts
* View product structures and digital mock-ups

A disabled user cannot do anything.

To update user or group access, check the related checkbox and click on the desired action button (remove, disable, enable...) below the list.

###Managing Groups

Groups are useful when the number of users tends to increase. They can hold the same kind of permissions.

Just click on group's name to open the detail view. You can then add or remove users within the selected group.

{% image /assets/images/documentation/en/group_user_management.png "Group Users Management"%}

##Access Control List

###Documents and Parts

If newly created documents and parts are accessible according to the permissions defined at workspace level, it’s possible to override them by selecting the "ACL" tab. From that panel you can upgrade or downgrade access rights to any user or group in the workspace for the specific entity (document or part). The lower level is "forbidden" which means that the entity will not be visible by the user or group.

{% image /assets/images/documentation/dev/en/document_creation.png "Document creation, ACL tab"%}

Only the administrator of the workspace and the authors can modify the permissions of existing entities.
Once you've selected an entity the following icon appears in the banner at the top.

{% image /assets/images/documentation/en/permissions.png%}

You can then change the permissions in the same way as creation time.

Entities holding specific rights display a prohibition sign at the end of the line. Green means you have full access to the entity, yellow means read-only access.

{% image /assets/images/documentation/dev/full_access.png "Full access"%}
{% image /assets/images/documentation/dev/read_only.png "Read only"%}

###Templates

If you have full access to a created template, you can change its permissions to any user or group in the workspace. By setting read only permission to a user or group, the user or group will only be able to attach it to an entity. By setting forbidden permission, the user or group will never see that template.

###Workflows

If you have full access to a created workflow, you can change its permissions to any user or group in the workspace. By setting read only permission to a user or group, the user or group will only be able to use it in a template or entity. By setting forbidden permission, the user or group will never see that workflow.

##Combined Access Rights

Important concepts:

* Access rights priority order:
1. User rights on a document / part
2. Group rights on a document / part
3. User rights on the workspace
4. Group rights on the workspace
5. Rights of the most permissive group
* Access rights are useless for users disabled on workspace.
* The workspace administrator exceeds these rights.

Below the summary tables of possible combinations.

###User present in one group

| Group rights | User rights on Workspace | Effective rights |
| ------------ | ------------------------ | ---------------- |
| full access  | read only                | read only        |
| full access  | full access              | full access      |
| read only    | read only                | read only        |
| read only    | full access              | full access


###User present in several groups

| Group I rights | Group II rights | Effective rights |
| -------------- | --------------- | ---------------- |
| full access    | full access     | full access      |
| full access    | read only       | full access      |
| full access    | disable         | full access      |
| read only      | disable         | read only        |
| read only      | read only       | read only

###User access rights for a document/part

| User rights on Workspace | User Rights on Document/Part | Effective Rights |
| ------------------------ | ---------------------------- | ---------------- |
| full access              | full access                  | full access      |
| full access              | read only                    | read only        |
| full access              | forbidden                    | forbidden        |
| read only                | full access                  | full access      |
| read only                | read only                    | read only        |
| read only                | forbidden                    | forbidden

###Group access rights for a document/part

| Group rights on Workspace | Group Rights on Document/Part | Effective Rights |
| ------------------------- | ----------------------------- | ---------------- |
| full access               | full access                   | full access      |
| full access               | read only                     | read only        |
| full access               | forbidden                     | forbidden        |
| read only                 | full access                   | full access      |
| read only                 | read only                     | read only        |
| read only                 | forbidden                     | forbidden        |

#Document Management

DocDokuPLM has a document management module that includes a comprehensive versioning system (master, revision and iteration), functions for sharing, publishing documents, treeview and tags organization, ACL configuration...
In the following paragraph, we will detail all of these functionalities.

{% image /assets/images/documentation/dev/en/image00.png "Document management menu"%}

##Document template

###Document template creation

You can create templates that will be used to instantiate documents. You can choose to restrict document naming by filling a mask format and selecting the identifier generation option. This will lead to an automatic creation of identifiers for documents using the template.

{% image /assets/images/documentation/dev/en/image25.png "Document template creation form"%}

###Adding a workflow

Applying a workflow to a template will automatically set the workflow to the new document instantiated with that template.

###Adding files and attributes

You can define attribute types in the template and attach files to it. All documents created with the same template will have the same attributes set and attached files. Attribute values will be set on those documents and obviously, files will evolve independently.

{% image /assets/images/documentation/dev/en/image42.png "Attaching files to the template"%}

## Document creation

Each documents must belong to a folder. To create a new document in a specific directory, you must first select the directory then click on the “New document“ button.

{% image /assets/images/documentation/dev/en/image09.png "Document creation form"%}

When creating a document, you can edit its attributes, specify a workflow and set specific access rights. Note that you will not be able to upload files or link the current document to another until you finish the creation process.

Once the document is created you can perform the following actions:

* Check-in / Undo check-out / Check-out
* Deletion
* Subscription to document state change notifications. In this case the user receives an email each time a change is made by other users on the document
* Subscription to iteration change notifications. The user receives a notification when there is a new iteration on the document
* Adding tag to documents - for example, classifying a document as important
* Access rights management
* New version creation
* Public or private document publishing

##Document move

You can move a document to another directory with the below icon. To do so just drag and drop the document from the icon to the targetted folder.

{% image /assets/images/documentation/dev/document_move.png "Move button"%}

##Document modification

In order to modify a document, you must first reserve it. You can access the document modification window by clicking on its title in the list.

The arrows at the bottom left of the window allow you to visualize the different changes done in previous iterations.

You can open the directory containing the document by clicking on the “Folder“ info link.

{% image /assets/images/documentation/dev/en/image10.png "Document details window"%}

###Attributes tab

###Files tab

This tab allows you to associate files.

{% image /assets/images/documentation/dev/en/image52.png "Files view"%}

A file can be renamed by clicking on the small pencil. The new title will be registered only if you click on the check button.

{% image /assets/images/documentation/dev/file_rename.png "File renaming"%}

You can download a file by clicking on its name and delete files by selecting the related checkboxes.

{% image /assets/images/documentation/dev/file_delete.png "File deletion"%}

##Document conversion

In addition to the mentioned features, DocDokuPLM can convert attached files into pdf. The majority of word processing formats are supported.

##“Checked out” and “Tasks” links

To ensure fast access to documents, you will find two shortcut links in the left menu:

* Checked out: this link displays all the documents reserved by the current user
* Tasks: this link shows the documents the user is directly involved in through a workflow

{% image /assets/images/documentation/en/image06.png "Links section"%}

#Product Management

DocDokuPLM is a management system for collaborative product development which purpose is to help members of the same organization create and exchange data around products.

The product management module offers, among others, the following features:

* Configuration management
* Product structure exploration
* 3D digital mock-up visualization
* Parts metadata
* Part-document links

Parts and products creation is explained below.

##Product structure

The product structure is a breakdown showing the various items that compose a product.
These components are named parts, they are assemblies if they are made of other parts. Within DocDokuPLM parts can be created from scratch or imported from CAD tools.

###Part template creation

Sometimes, it’s interesting to ensure that parts are always filled with predefined properties (workflow, CAD file, attributes) or their reference number respects a given formalism. To enforce such constraints you have to create parts from templates.

###Part creation

As seen, part creation panel has an optional template property but there are also several other input fields like name, description, attributes, workflow (see paragraph below) or ACL (Access Control List).

{% image /assets/images/documentation/dev/en/part.png "Part creation"%}

The newly created part will be added to the list.

{% image /assets/images/documentation/dev/en/part_list.png "Parts list"%}

From the list, a click on the part number will bring the details window to the front. From that screen, you can modify (if you checked out the part) the following elements: attributes, the CAD file and links to documents.

By selecting a part, you can apply a set of actions including:

* Check-out / Undo check-out / Check-in
* Deletion
* Adding tag to parts - for example, classifying parts as important
* Access rights management
* New version creation
* Release

###Part CAD File

This tab allows you to associate a CAD file to the part. If you choose a file while another was already set, the older file will automatically be replaced with the new one.

{% image /assets/images/documentation/dev/en/image51.png "CAD File view"%}

###Part assembly

When modifying a part, you can edit the assembly composition.

An assembly is composed of other parts.

{% image /assets/images/documentation/dev/en/part_assembly.png "Part assembly"%}

###Notifications

###Quick links

You have a fast access to your checked out parts in the left menu.

{% image /assets/images/documentation/dev/en/image50.png "Links section"%}

##Product creation

The creation of a product involves supplying an identifier and a part number, filling a description is optional.

The part number designates the root part of your product. It can be a simple part or a parts assembly.

{% image /assets/images/documentation/dev/en/product_creation.png "Product creation form"%}

The new product will be added to the product list. Selecting an item from that list proposes two actions: deletion and baseline creation.

##Product explorer

The product structure is displayed as a tree view where each node represents an assembly which is expandable. The node itself is clickable in order to display its main properties.

{% image /assets/images/documentation/en/tree_structure.png "Tree structure of a product"%}

Sometimes, especially for complex products, locating a part in the tree could be cumbersome. Look at the above example. To facilitate this operation, there is a search bar on the top left allowing you to easily find a part from its number.

{% image /assets/images/documentation/en/search_bar.png "Search bar"%}

As an alternative, you can select the part directly on the 3D scene.

One click on a 3D object selects the results on the left hand panel. The associated part and all its ancestors will be highlighted in yellow. Moreover the part properties are displayed in the right hand panel.
This feature is useful when the user wants to find a part he ignores the part number.

{% image /assets/images/documentation/dev/en/visualization.png "3D model visualization"%}

The possible actions in the 3D visualization mode are:

* Creating markers to report a design issue for example
* Creating layers that hold a set of markers
* Export 3D visualization of a part. Produces the html code to embed in other web pages (like YouTube or Google Maps)

##Baseline creation

Baselines are kinds of snapshots of the entire product structure at a given time so you can manage different versions of the same product.

{% image /assets/images/documentation/dev/en/image40.png "Baseline creation form"%}

2 configuration types are offered :

* Latest checked in, to include the last checked in iterations of each implicated part
* Latest released, to include automatically the last released versions of each implicated part. If several versions exist for articles then the Versions tab gives you the opportunity to select an older version.

{% image /assets/images/documentation/dev/baseline_versions.png "Version selection"%}

Furthermore the Configuration tab offers you to choose between a part or one of its substitutes or even nothing, if the part is optional.

{% image /assets/images/documentation/dev/en/image58.png "Configuration selection"%}

#Workflow Management

A workflow is a representation of the various tasks that need to be completed and their interactions. These operations are assigned to different users belonging to the same workspace and are related to an identified document or part.

##Roles

DocDokuPLM workflows are role-based. This means that to increase the applicability of any workflow model, task assignees are not expressed directly by user names but rather by roles.

Thus, the first step involved in workflow creations is to define the roles used inside the workspace. These roles can optionally be mapped to a default user assignee. Anyway, when the workflow model is instantiated and attached to a document or a part, we will have the opportunity to refine those mappings.

{% image /assets/images/documentation/en/image32.png "Roles definition panel"%}

##Workflow template

A workflow template (or model) lists several activities from an initial state to a final state. Each activity contains a label naming its intermediate state and a list of tasks to complete. Those tasks can be performed in series or in parallel.

For a serial activity, the tasks are performed sequentially. If one task is rejected, the current activity is stopped.

For a parallel activity, the tasks are simultaneously open and as a consequence can be closed in any order. A rejected task does not necessarily lead to stop the current activity. In effect, parallel activities have an additional property which is the number of done tasks needed to progress to the next activity. This number ranges from 1 to the total number of tasks.

Validating an activity results to start the next one. Invalidating an activity results in the suspension of the entire workflow.

In case of an unvalidated activity, the workflow will go on the recovery activity if one has been previously defined.

A workflow template can be changed at any time. That will have no incidence to the already instantiated workflows.

{% image /assets/images/documentation/dev/en/image12.png "Workflow template creation"%}

##Workflow instance

When creating a document or a part, the author can choose the workflow template he wants to apply. All the implied roles can then be respecified.

{% image /assets/images/documentation/dev/en/image41.png "Roles definition during document creation"%}

Once the document or part has been created, the associated workflow (if any) starts on the first activity. When a task has been opened, a mail is sent to the current task responsible user so he can approve or reject it and sign.

##Lifecycle state

Once an activity is started, every task assignee receives a mail which includes a full description of the task to complete.

{% image /assets/images/documentation/dev/en/image46.png "Workflow instantiated on a document"%}

A running task can be marked as done or rejected if:

* the responsible of the task has downloaded at least once an associated file
* the document or the part is released (not checked out)

All the users who have subscribed to state change notification will be informed by email.

#Check-out / Check-in

To lock a document/part to prevent modification, just select it and press the check-out button. A new item iteration will be created.

{% image /assets/images/documentation/image14.png "Buttons check-out / undo check-out / check-in"%}

A checked out item cannot be edited by other users. To validate the modifications you will have to check it in. Otherwise, you can cancel the changes with the undo check-out action.

While releasing (check-in operation) the item, you have a chance to enter an optional revision note. If you do not want to fill a note, press the "Ignore" button.

{% image /assets/images/documentation/en/image19.png "Revision note window"%}

All these actions can be performed in the “Iteration“ tab on the item details window.

{% image /assets/images/documentation/dev/en/image49.png "Buttons Check in and Cancel checkout"%}

#List of values

DocDokuPLM allows you to predefine values of attributes, called list of values, you will then be able to use as attributes for a document, a part or a template. To create or edit values, click on the following icon shown on the templates page :

{% image /assets/images/documentation/dev/edit_lov.png "Button Lists of values"%}

For example, you can create attributes values dedicated for colors.

{% image /assets/images/documentation/dev/en/image56.png "Lists of values window"%}

Once saved, the list is accessible through the Attributes tab of the template or entity detail window. By attributing a list of values to a template or entity, you create a new instance of this list.

{% image /assets/images/documentation/dev/en/image57.png "List of values selection"%}

You will not be able to :

* delete a list of values which has instances
* edit an instance of list of values

#Files Management

A click on the following icon opens the details window of a document or a part or a template at the Files tab.

{% image /assets/images/documentation/dev/file_icon.png "Files quick access"%}

Any file - associated with any part or document or tempate - can be renamed by clicking on the small pencil. The new title will be registered only if you click on the check button.

{% image /assets/images/documentation/dev/file_rename.png "File renaming"%}

You can download a file by clicking on its name and delete files by selecting the related checkboxes.

{% image /assets/images/documentation/dev/file_delete.png "File deletion"%}

Do not forget to press on the modal Save button to validate your modifications.

#Documents Links Management

You can easily add references to documents during part/document edition. Links can be managed in the “Links“ tab on the item modification window.

{% image /assets/images/documentation/dev/en/image53.png "Links Management"%}

You comment a document link by clicking on the small pencil. The comment will be registered only if you click on the check button.

{% image /assets/images/documentation/dev/en/image54.png "Comment a link"%}

{% image /assets/images/documentation/dev/en/image55.png "Commented link"%}

#Viewer or permalink

Each document/part provides a permanent link where you see details of its latest revision. To get there, you should simply click on the title of the entity window.

{% image /assets/images/documentation/en/image22.png %}

You can explore all properties of the entity as well as visualize their attached files. The viewer supports a large number of formats: pdf, jpg, mp4, doc... Files not supported by the viewer will be downloaded.

{% image /assets/images/documentation/en/image02.png "Document permalink"%}

#Tags

You have the possibility to tag documents/parts. To do so, select one or more items and press the tag icon:

{% image /assets/images/documentation/en/image27.png %}

From the tag management window, you can affect existing tags or new ones.

{% image /assets/images/documentation/dev/en/image34.png "Tags window"%}

To display the items associated with a specific tag, select that tag from the left menu.

{% image /assets/images/documentation/en/image37.png "Tag selection"%}

You can delete a tag by clicking on the right arrow into the area of the tag, then click on “Delete”. The tag will be removed but the associated items will not.

{% image /assets/images/documentation/en/image39.png "Tag deletion"%}

#Search

We distinguish two types of search: quick and advanced.

##Quick search

The quick search bar appears on top of the documents/parts list. It lets you quickly find an item from its reference or name.

{% image /assets/images/documentation/en/image08.png "Quick search bar"%}

##Advanced search

There are two ways to get access to the advanced search:

* through the “Search” link from the left menu, only for documents
* through the small arrow from the quick search bar

This advanced search allows you to find an item from its name, type, identifier, version, author, creation date or content files.

{% image /assets/images/documentation/dev/en/image30.png "Advanced search"%}

#Sharing and publishing

##Publishing

Each document/part can be published. To do so, click on the right icon on the item table row.

{% image /assets/images/documentation/en/publish.png %}

The following window will appear:

{% image /assets/images/documentation/dev/en/image21.png "Publishing window"%}

By activating the public share, the item is publicly accessible from the Internet.

##Private access

You may also want to generate a private link optionally protected by a password or an expiration date. For that, just fill the password and/or expiration date and push the share button.

{% image /assets/images/documentation/en/image07.png "Private share"%}

The generated link is obfuscated, it cannot be guessed.

{% image /assets/images/documentation/en/image48.png "Generated link"%}