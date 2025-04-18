---
summary: OutSystems Developer Cloud (ODC) offers manual and automatic data replacement options for app screens, enhancing customization and functionality.
tags: data management, screen templating
locale: en-us
guid: 6fccfc68-813b-45a4-a938-4f740a10176c
app_type: mobile apps, reactive web apps
platform-version: odc
figma:
audience:
  - mobile developers
  - frontend developers
  - full stack developers
outsystems-tools:
  - odc studio
content-type:
  - procedure
---

# Replace data in screens

Once you’ve built an app that contains screen templates or accelerators, you may want to replace the data in your screens with your own data. Data can be replaced [manually](#replace-data-manually) or [automatically](#replace-data-automatically). 

## Replace data automatically

Automatic replacement works in Form, Table, List, and Gallery widgets. You can automatically replace data in your screen by dragging and dropping an entity to the widget that supports automatic data replacement.

1. Drag and drop the data source entity that contains your data to the widget for which you want to replace the data.

    **Note**: You can only drag and drop one entity at a time.

1. After dragging and dropping the new entity to the widget, check that the widget displays all of the correct attributes.

    You can drag and drop any missing attributes or entities that are related to the  data source you added in step 1.

1. Verify that the widget labels correspond to the data and edit the labels or expressions if necessary.

    For example, when using the Table widget, check that the information of each Header Cell corresponds to the information displayed in the related cell. 

1. Check any logic associated with the widget, for example, a dropdown filter in a Table, and replace the data (List property) manually. 

1. Check the **TrueChange** tab for errors and warnings and fix them.

When replacing data inside a **Mobile App** screen that has been created from a screen template or accelerator, you can only replace server data with server data and local data with local data. Replacing data by dragging and dropping does not work with mixed data sources.

## Replace data manually

Manually replacing data allows you to have full control over the changes you make on the screen. To replace data, follow these steps: 

1. Compare the screen with your data model and remove the UI elements you don't need. 

    Removing these UI elements reduces the number of warnings and errors in the later steps.

1. Delete the data source entities.
    * For screens that use data actions:

        * Open the data action

        * Delete the aggregates you don’t need

        * Add your own data fetching, for example, aggregates or SQL, to the action flow and apply any necessary filtering


    * For screens that use aggregates:

        * Delete the aggregates you don’t need

        * Add your own data fetching, for example, aggregates or data action to the screen and apply any necessary filtering


1. Check the TrueChange tab for errors and warnings and fix them.
