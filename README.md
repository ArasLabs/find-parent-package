# Find Parent Package

The Find Parent Package project provides an Item Action that determines the name of the context item's parent PackageDefinition. The import package contained in this project imports the labs_FindParentPackage Method and the labs_FindParentPackage Action. The package also adds the labs_FindParentPackage Action to the following ItemTypes:

* Action
* CommandBarSection
* Form
* Grid
* Identity
* ItemType
* Life Cycle Map
* List
* Method
* Permission
* PresentationConfiguration
* RelationshipType
* Report
* Sequence
* SQL
* Workflow Map

## Project Details

**Built Using:** Aras 11.0 SP7
**Browsers Tested:** Internet Explorer 11, Firefox 38 ESR, Chrome

> Though built and tested using Aras 11.0 SP7, this project should function in older releases of Aras 11.0 and Aras 10.0.

## Installation:

#### Important!
**Always back up your code tree and database before applying an import package or code tree patch!**

### Pre-requisites:

1. Aras Innovator installed (version 11.0 SPx preferred)
2. Aras Package Import tool
3. Find Parent Package import package

### Steps to Install:

1. Backup your database and store the BAK file in a safe place.
2. Open up the Aras Package Import tool.
3. Enter your login credentials and click **Login**
  * _Note: You must login as root for the package import to succeed!_
4. Enter "Find Parent Package" in the TargetRelease field.
  * Optional: Enter a description in the Description field.
5. Enter the path to your local `..\FindParentPackage\Import\imports.mf` file in the Manifest File field.
6. Select **aras.labs.FindParentPackage** in the Available for Import field.
7. Select Type = **Merge** and Mode = **Thorough Mode**.
8. Click **Import** in the top left corner.
9. Close the Aras Package Import tool.

You are now ready to login to Aras and use the Find Parent Package action.

## Usage

The Find Parent Package action is accessible from the Action menu in the Aras main window, the main grid context menu, and the Action menu in the Item tear-off window. The steps below show how to use the Find Parent Package action in the Aras main window Action menu.

1. Login to Aras as an administrator (ex: admin).
2. Navigate to **Administration > Methods** in the Table of Contents (TOC).
3. Search for the labs_FindParentPackage Method in the main grid.
4. Select the labs_FindParentPackage Method in the main grid.
5. Click **Action** in the main menu and select **Find Parent Package**.

The action will return an alert dialog indicating that the parent package is *aras.labs.FindParentPackage*.

## Customize

You can use the Find Parent Package with additional ItemTypes by adding the labs_FindParentPackage Action to the Action tab on the ItemType.

Alternatively, you can execute the following AML in Nash or AML Studio.

```xml
<AML>
	<Item type="Item Action" action="add">
		<source_id>
			<Item type="ItemType" action="get" select="id" where="[ItemType].name='YourItemTypeHere'" />
		</source_id>
		<related_id>7E41725E177B4C04ADF87906B033900F</related_id>
	</Item>
</AML>
```
> Remember, only metadata items should be added to PackageDefinitions.
>For more information on packages and the types of items they should include, please see the Aras Package Import Export Utility documentation.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

For more information on contributing to this project, another Aras Labs project, or any Aras Community project, shoot us an email at araslabs@aras.com.

## License

Aras Labs projects are published to Github under the MIT license. See the [LICENSE file](./LICENSE.md) for license rights and limitations.
