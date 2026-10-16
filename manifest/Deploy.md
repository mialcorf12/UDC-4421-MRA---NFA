# turn off process failed, first disabled, deploy, enabled
Version 14: Invite Customer - Contact Updates
Version 3: Send to NetSuite - Contact
Version 5: Update ASD Email
ValidationRule Onboarding_Account_Owner 

# new changes
## UDC-4446 NFA Reva and Zendura
- Desactivate
    - Process Builder - New Customer Feature Flag Update - NFA
    - Process Builder - NFA Create
- Activate 
    - Flow Builder NFA Creation - V1
    - Flow Builder NFA Send to WebApp Update - V1








# ?????? Process Builder - Create MRAs for New Accounts ?????


# post deploy task
- field visibility
- add fields in a new layout section
- enable flow
- add conditions in Account and Contact Duplication Rules = Current User: Usernamenot equal toapiuser@ulabsystems.com.staging

## flows replacing Process Builders (deployed as Draft)
- NFA Creation (Account) replaces Parent_Account_Checkbox
- NFA Send to WebApp Update (New_Feature_Association__c) replaces New_Customer_Feature_Flag_Update_NFA
- cutover: deactivate both Process Builders first, then activate both flows (avoid double execution)
- verify the uLab Feature IDs in NFA Creation exist in the target org (a54Rh00000CzdToIAJ, a546g000000qt17AAA)









# no need changes
- Process Builder - New Customer Feature Flag Update - NFA
- Process Builder - Create MRA send to Boomi
- Process Builder - Create Futures MRA
