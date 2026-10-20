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
- Desactivate
    - Process Builder - New Customer Feature Flag Update - NFA
    - Process Builder - NFA Create
- Activate 
    - Flow Builder NFA Creation - V1
    - Flow Builder NFA Send to WebApp Update - V1
- Delete
    - Flow Builder New Acct Auto Create NFA - V1




# UDC-4421 KAI MR y MRA
## 1) New KAI fields
    - KAI_2_Retainer_Bundle__c
    - KAI_4_Retainer_Bundle__c
    - KAI_5_Retainer_Bundle__c
    - KAI_Aligner_Price__c
    - KAI_Comprehensive_Bundle__c
    - KAI_Mild_Bundle__c
    - KAI_Retainer_Price__c
    - KAI_STL_Price__c
    - KAI_uAdjust_10_Bundle__c

## set FLS
## deploy pagelayout y flexipage
    - Marketing Program Layout
    - Marketing_Reward_Record_Page

    - Marketing_Reward_Association_Record_Page-> cambia nombre a -> MRA_Program_Association
    - Marketing_Reward_Association_Record_Page1 -> cambia nombre a -> MRA_Promotion_Association
    set org default


# 2) Records MR
    - KAI
    - Fresh Start MRA
    - STL100
    - uAssist 100 MRA
    - STLONE MRA 

# 3) no need changes
- Process Builder - Version 18: Create Futures MRA - Active
- Process Builder - Version 4: Create MRA send to Boomi	- Active
- Process Builder - Version 18: Create MRAs for New Accounts - Inactive    *** ATTENTION ***
- Process Builder - Version 16: Create MRA when uD7 date added to Company - Inactive

# 4) new Flow Builder 
- Flow Builder - Create KAI MRAs - V1

# 5) WITH changes
- Flow Builder - Create MRAs for New Accounts - V3 - Active


- Flow Builder - Record Trigger - Copy pricing fields on MRA record from MR record on Effective date - V8
- Flow Builder - Copy pricing fields on MRA record from MR record on Effective date - V8


