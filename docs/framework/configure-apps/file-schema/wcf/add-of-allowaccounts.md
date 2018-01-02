---
title: "&lt;allowAccounts&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 064c9d438832142e1f761d0d33db528dbe73ef2a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a>&lt;allowAccounts&gt;의 &lt;add&gt;
[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 호스트하고 공유 서비스에 대한 연결 액세스 권한이 부여된 프로세스를 수행할 수 있는 사용자 계정을 지정합니다.  
  
 \<system.serviceModel.activation >  
  
## <a name="syntax"></a>구문  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|securityIdentifier|사용자 계정을 식별하는 데 사용하는 고유 식별자를 지정하는 문자열입니다. 반환되는 기본값은 LocalSystem, Administrators, NS, LS 및 IIS_USRS입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<allowAccounts >](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|`securityIdentifier` 서비스를 호스트하고 공유 서비스에 대한 연결 액세스가 부여된 프로세스의 사용자 계정을 지정하기 위한 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 특성이 포함된 구성 요소 컬렉션입니다.|  
  
## <a name="example"></a>예  
 다음 구성 예제에서는 사용자 계정에 대한 다섯 가지 기본 식별자를 이 컬렉션에 추가합니다.  
  
```xml  
<allowAccounts>  
   // LocalSystem account  
   <add securityIdentifier="S-1-5-18"/>  
   // LocalService account  
   <add securityIdentifier="S-1-5-19"/>  
   // Administrators account  
   <add securityIdentifier="S-1-5-20"/>  
   // Network Service account  
   <add securityIdentifier="S-1-5-32-544" />  
   // IIS_IUSRS account (Vista only)  
   <add securityIdentifier="S-1-5-32-568"/>  
</allowAccounts>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
