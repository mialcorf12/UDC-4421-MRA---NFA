# turn off process failed, first disabled, deploy, enabled
Version 14: Invite Customer - Contact Updates
Version 3: Send to NetSuite - Contact
Version 5: Update ASD Email
ValidationRule Onboarding_Account_Owner 

# UDC-4446 NFA Reva and Zendura
## 1) Records NFA
    - No Zendura
    - Reva

## 2) new changes
- DEPLOY AND Activate 
    - Flow Builder NFA Creation - V1
    - Flow Builder NFA Send to WebApp Update - V1

- Desactivate
    - Process Builder - New Customer Feature Flag Update - NFA
    - Process Builder - NFA Create
- Delete
    - Flow Builder New Acct Auto Create NFA - V1







# UDC-4421 KAI MR y MRA
## 1) New KAI fields
    - KAI_2_Retainer_Bundle__c
    - KAI_4_Retainer_Bundle__c
    - KAI_5_Retainer_Bundle__c
    - KAI_Comprehensive_Bundle__c
    - KAI_Mild_Bundle__c
    - KAI_STL_Price__c
    - KAI_uAdjust_10_Bundle__c

- account fields needs update the MR id
    - KAI_MRA_assigned__c
    - UDC_MRA_assigned__c


## set FLS
## deploy flexipage (lightning record pages)
    - Marketing_Reward_Record_Page-> cambia nombre a -> MR_Program_Association
    - Marketing_Reward_Association_Record_Page-> cambia nombre a -> MRA_Program_Association
    - Marketing_Reward_Association_Record_Page1 -> cambia nombre a -> MRA_Promotion_Association
    set all as org default


# 2) KAI MR record
SELECT Id, RecordTypeId, RecordType.Name, Name__c, Brief_Description__c, Status__c, Start_Date__c, End_Date__c, Aligner_Price__c, Retainer_Price__c, KAI_STL_Price__c, KAI_Mild_Bundle__c, KAI_Comprehensive_Bundle__c, KAI_uAdjust_10_Bundle__c, KAI_2_Retainer_Bundle__c, KAI_4_Retainer_Bundle__c, KAI_8_Retainer_Bundle__c, NetSuite_Price_Level__c, NS_Enhanced_Price_Level__c from Marketing_Reward__c where Name__c='KAI'


# 3) no need changes
- Process Builder - Version 18: Create Futures MRA - Active
- Process Builder - Version 4: Create MRA send to Boomi	- Active
- Process Builder - Version 18: Create MRAs for New Accounts - Inactive    *** ATTENTION ***
- Process Builder - Version 16: Create MRA when uD7 date added to Company - Inactive

# 4) new Flow Builder 
- Flow Builder - Create KAI MRAs - V1

# 5) WITH changes
- Flow Builder - Create MRAs for New Accounts - V3 - Active
- Flow Builder - Copy pricing fields on MRA record from MR record on Effective date - V9
- Flow Builder - Record Trigger - Copy pricing fields on MRA record from MR record on Effective date - V9





# 6) create new KAI Program Bundle UDC-5092
SELECT Name, Description__c, Option_Type__c, Status__c, Type__c, Effective_Date__c, End_Date__c, NS_Internal_Id__c, Aligner_Qty__c, Retainer_Qty__c, Template_Qty__c, Custom_Packaging_Qty__c, Standard_Shipment_Qty__c, Premium_Shipping_Qty__c, Shipping_Surcharge_Qty__c FROM ProductBundles__c WHERE Name like 'KAI%'

# 7) create new KAI Program Bundle Associations associated with KAI MR
Link 6 to 2
SELECT Marketing_Reward__r.Name__c, Bundle__r.Name, Marketing_Reward__c, Bundle__c, Bundle_Type__c, Effective_Date__c, End_Date__c, custrecord_included_in_kai__c, custrecord_udesign_cloud_bundle_type__c, custrecord_udesign_cloud_bundle_label__c, Send_to_Boomi__c FROM Program_Bundle_Associations__c WHERE Program_Name__c='KAI' ORDER BY Bundle__r.Name