# Ineiman Magento 2 Base Module
## Usage

Used to define main methods wich will be used in **every** project and as a placeholder for store config menu.

### Store config menu example

Create file `app/code/Ineiman/MODULENAME/etc/adminhtml/system.xml` and add following *(replace `MODULENAME` width real module name)*:

```xml
<?xml version="1.0"?>
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:noNamespaceSchemaLocation="urn:magento:module:Magento_Config:etc/system_file.xsd">
    <system>
        <section id="ineiman_MODULENAME" translate="label" type="text" sortOrder="20" showInDefault="1" showInWebsite="0" showInStore="0">
            <label>MODULE MENU TITLE</label>
            <tab>ineiman</tab>
            <resource>Ineiman_Base::ineiman_base</resource>
            <group id="MODULENAME_general" translate="label" type="text" sortOrder="10" showInDefault="1" showInWebsite="0" showInStore="0">
                <label>General Settings</label>
                <field id="MODULENAME_enabled" translate="label" type="select" sortOrder="10" showInDefault="1" showInWebsite="0" showInStore="0">
                    <label>MODULENAME Enabled</label>
                    <source_model>Magento\Config\Model\Config\Source\Yesno</source_model>
                </field>
            </group>
        </section>
    </system>
</config>
```

### Admin panel menu example

Create file `app/code/Ineiman/MODULENAME/etc/adminhtml/menu.xml` and add following *(replace `MODULENAME` width real module name)*:

```xml
<?xml version="1.0"?>
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:noNamespaceSchemaLocation="urn:magento:module:Magento_Backend:etc/menu.xsd">
    <menu>
        <add id="Ineiman_MODULENAME::ineiman_modulename"
             title="MODULENAME"
             resource="Ineiman_MODULENAME::ineiman_modulename"
             parent="Ineiman_Base::ineiman_base"
             module="Ineiman_MODULENAME"
             sortOrder="20"/>
        <add id="Ineiman_MODULENAME::modulenamesettings"
             title="Settings"
             resource="Ineiman_MODULENAME::modulenamesettings"
             module="Ineiman_MODULENAME"
             parent="Ineiman_MODULENAME::ineiman_modulename"
             action="adminhtml/system_config/edit/section/ineiman_modulename"
             sortOrder="10"/>
    </menu>
</config>
```
