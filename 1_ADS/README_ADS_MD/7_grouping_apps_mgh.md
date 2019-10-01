# AWS Application Discovery Service & Migration Hub Lab


---

© 2020 Amazon Web Services, Inc. and its affiliates. All rights reserved. This work may not be reproduced or redistributed, in whole or in part, without prior written permission from Amazon Web Services, Inc. Commercial copying, lending, or selling is prohibited.

Errors or corrections? Email us at onpremsimulator@amazon.com.


# Group applications on Migration HUB

Some of your discovered servers might need to be migrated together to remain functional. In this case, you can logically define and group discovered servers into applications.
As part of the grouping process, you can search, filter, and add tags.

✅ **Step-by-step Instructions**

**To group servers into a new or existing application**
The following steps will demonstrate how to group applications using Migration Hub

1. Open AWS Console and Select Services, Migration & Transfer, Migration Hub
2. In the Migration Hub navigation pane, choose **Servers**.
3. In the servers list, select each server that you want to group into a new or existing application. Use the information obtained in the Athena analysis exercise.
4. Optional: For each selected server, choose **Add tag**, type a value for **Key**, and then optionally type a value for Value.
5. Choose Group as application to create your application, or add to an existing one.
6. In the **Group as application** dialog box, choose Group as a new    application or Add to an existing application.
    1. If you chose **Group as a new application**, type a name for Application name. Optionally, you can type a description for **Application description**.
    2. If you chose **Add to an existing application**, select the name of the application to add to in the list.
7. Choose **Save**.

&nbsp;


⭐️ Tips

💡 Repeat the steps above grouping the applications you just discovered in your enviromnent.

💡 Use reports created in Athena to group servers by afinity, as a WEB Server with it related Database Server.

💡 Explore the "EC2 Instance Recommendations" in the Migration Hub to see the suggested instance types for the servers your collected.

**Your servers now are ready to plan for migration.**

---

## This is the end of this module

&nbsp;
