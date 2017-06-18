# APP-V
Microsoft APP-V

How to enable APP-V on Windows 10

https://docs.microsoft.com/en-us/windows/application-management/app-v/appv-enable-the-app-v-desktop-client


FAQ
http://blog.eastern.nl/2016/08/run-or-enable-microsoft-app-v-client-on-windows-10-anniversary-update/


APP-V5.1


Publish  Office 2016 
--------------------


Set-AppvClientConfiguration –EnablePackageScripts 1

Add-AppvClientPackage ProPlusRetail_en-us_x86.appv | Publish-AppvClientPackage -Global


Publish App2 
-----------

Add-AppvClientPackage App2.appv | Publish-AppvClientPackage -Global


Deploying Connection Groups on the Client Machine

Add-AppvClientConnectionGroup group.xml | Enable-AppvClientConnectionGroup


Hit The following Error

Enable-AppvClientConnectionGroup : The operation failed because the virtual COM settings for the packages in the connection group
are not identical. Verify the virtual COM settings of the packages listed in the connection group and try again.
Operation attempted: Enable Connection Group.
AppV Error Code: 0A0003000F.
Please consult AppV Client Event Log for more details.
At line:1 char:43
+ Add-AppvClientConnectionGroup group.xml | Enable-AppvClientConnectionGroup
+                                           ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidResult: (:) [Enable-AppvClientConnectionGroup], ClientException
    + FullyQualifiedErrorId : EnableConnectionGroupError,Microsoft.AppV.AppvClientPowerShell.EnableAppvClientConnectionGroup

Unpublish-AppvClientPackage -Name appv2  -global

Change  DeploymentConfiguration same as office

 Add-AppvClientPackage appv2.appv -DynamicDeploymentConfiguration APPV2_DeploymentConfig.xml | Publish-AppvClientPackage -Global







References
----------

https://technet.microsoft.com/en-us/itpro/mdop/appv-v5/deploying-microsoft-office-2016-by-using-app-v


https://blogs.technet.microsoft.com/appv/2012/11/06/deploying-connection-groups-in-microsoft-app-v-v5/


http://www.appvirtguru.com/viewtopic.php?f=70&t=8093


