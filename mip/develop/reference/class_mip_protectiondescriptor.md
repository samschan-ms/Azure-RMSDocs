---
title: class ProtectionDescriptor 
description: Documents the protectiondescriptor::undefined class of the Microsoft Information Protection (MIP) SDK.
author: msmbaldwin
ms.service: information-protection
ms.topic: reference
ms.author: mbaldwin
ms.date: 03/30/2023
---

# class ProtectionDescriptor 
Description of protection associated with a piece of content.
  
## Summary
 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
public ProtectionType GetProtectionType() const  |  Gets type of protection, whether it originated from protection SDK template or not.
public std::string GetOwner() const  |  Gets owner for the protection.
public std::string GetName() const  |  Gets protection name.
public std::string GetDescription() const  |  Gets protection description.
public std::string GetTemplateId() const  |  Gets the protection template ID, if any.
public LabelInfo GetLabelInfo() const  |  Gets the label Info, if any.
public std::string GetLabelId() const  |  Gets the label ID, if any.
public std::string GetContentId() const  |  Gets the Content ID, if any.
public std::vector&lt;UserRights&gt; GetUserRights() const  |  Gets collection of users-to-rights mappings.
public std::vector&lt;UserRoles&gt; GetUserRoles() const  |  Gets collection of users-to-roles mappings.
public bool DoesContentExpire() const  |  Checks if content has an expiration time or not.
public std::chrono::time_point&lt;std::chrono::system_clock&gt; GetContentValidUntil() const  |  Gets protection expiration time.
public bool DoesAllowOfflineAccess() const  |  Gets if protection allows offline content access or not.
public std::string GetReferrer() const  |  Gets protection referrer address.
public std::map&lt;std::string, std::string&gt; GetEncryptedAppData() const  |  Gets app-specific data that was encrypted.
public std::map&lt;std::string, std::string&gt; GetSignedAppData() const  |  Gets the app-specific data that was signed.
public std::string GetDoubleKeyUrl() const  |  Gets the double key url to be used for custom protection.
public std::shared_ptr&lt;const std::vector&lt;uint8_t&gt;&gt; GetSerializedTemplate() const  |  Gets the serialized template, if any.
  
## Members
  
### GetProtectionType function
Gets type of protection, whether it originated from protection SDK template or not.

  
**Returns**: Type of protection
  
### GetOwner function
Gets owner for the protection.

  
**Returns**: Owner of protection
  
### GetName function
Gets protection name.

  
**Returns**: Protection name
  
### GetDescription function
Gets protection description.

  
**Returns**: Protection description
  
### GetTemplateId function
Gets the protection template ID, if any.

  
**Returns**: Template ID
  
### GetLabelInfo function
Gets the label Info, if any.

  
**Returns**: [Label](class_mip_label.md) Info
This property will be populated in ProtectionDescriptors for preexisting protected content & for UDP label based protection. It is a field populated by the server at the moment protected content is consumed. For UDP label based protection, its populated from label and tenant id values set by client.
  
### GetLabelId function
Gets the label ID, if any.

  
**Returns**: [Label](class_mip_label.md) ID
This property will be populated in ProtectionDescriptors for preexisting protected content & for UDP label based protection. It is a field populated by the server at the moment protected content is consumed. For UDP label based protection, its populated from labelId value set by client.
  
### GetContentId function
Gets the Content ID, if any.

  
**Returns**: Content ID
Publishing licenses will have this identifier surrounded by curly braces "{}". Those braces are removed from the value returned here
  
### GetUserRights function
Gets collection of users-to-rights mappings.

  
**Returns**: Collection of users-to-rights mappings
The value of the [UserRights](class_mip_userrights.md) property will be empty if the current user doesn't have access to this information (that is, if the user is not the owner and does not have the VIEWRIGHTSDATA right).
  
### GetUserRoles function
Gets collection of users-to-roles mappings.

  
**Returns**: Collection of users-to-roles mappings
  
### DoesContentExpire function
Checks if content has an expiration time or not.

  
**Returns**: True if content can expire, else false
  
### GetContentValidUntil function
Gets protection expiration time.

  
**Returns**: Protection expiration time
  
### DoesAllowOfflineAccess function
Gets if protection allows offline content access or not.

  
**Returns**: If protection allows offline content access or not (default = true)
  
### GetReferrer function
Gets protection referrer address.

  
**Returns**: Protection referrer address
The referrer is a URI that is displayable to the user if they cannot unprotect the content. It contains information on how that user can gain permission to access the content.
  
### GetEncryptedAppData function
Gets app-specific data that was encrypted.

  
**Returns**: App-specific data
A [ProtectionHandler](class_mip_protectionhandler.md) may hold a dictionary of app-specific data that was encrypted by the protection service. This encrypted data is independent of the signed data accessible via ProtectionDescriptor::GetSignedAppData.
  
### GetSignedAppData function
Gets the app-specific data that was signed.

  
**Returns**: App-specific data
A [ProtectionHandler](class_mip_protectionhandler.md) may hold a dictionary of app-specific data that was signed by the protection service. This signed data is independent of the encrypted data accessible via ProtectionDescriptor::GetEncryptedAppData.
  
### GetDoubleKeyUrl function
Gets the double key url to be used for custom protection.

  
**Returns**: Double key url
The double key URL that is used in custom requests to protect information with a second key. Needed for key generation.
  
### GetSerializedTemplate function
Gets the serialized template, if any.

  
**Returns**: Serialized template.