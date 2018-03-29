# Overview

#Important Notes
1. The preseed xml files in answer_files/ must have the correct information about the image 
in the iso you are using. To get this information, you must mount the iso (e.g. as d:) and:

    Dism /Get-ImageInfo /ImageFile:D:\sources\install.wim

as administrator. The "Name" of the Image you plan to use should be include in this tag:

					<InstallFrom>
						<MetaData wcm:action="add">
							<Key>/IMAGE/NAME</Key>
							<Value>THIS IS THE IMAGE NAME FROM THE DISM CALL</Value>
						</MetaData>
					</InstallFrom>

See [here](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/deployment-image-servicing-and-management--dism--command-line-options) and [here](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/automate-windows-setup) for more information.
