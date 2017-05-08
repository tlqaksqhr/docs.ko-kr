---
title: "완화: MemberDescriptor.Equals | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf3735f0-0dd4-4bef-b4b0-575264e10f39
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 409f06f4dfbe7be50dd2c487e49d3d4d8a477539
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-memberdescriptorequals"></a>완화: MemberDescriptor.Equals
[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터는 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 메서드의 구현이 변경되었습니다. `System.ComponentModel.EventDescriptor.Equals` 및 `System.ComponentModel.PropertyDescriptor.Equals` 메서드는 기본 클래스 구현을 상속하므로 이러한 변경 내용이 이러한 메서드에도 적용됩니다.  
  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이전 버전의 .NET Framework를 대상으로 하는 앱에서는 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 메서드의 같음 테스트 한 개체의 <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> 속성을 다른 개체의 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> 속성과 잘못 비교했습니다. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터, <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 메서드는 두 개체의 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> 속성을 비교합니다.  
  
## <a name="impact"></a>영향  
 이러한 변경은 <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> 개체에 대한 같음 테스트를 올바르게 구현하고 영향을 최소화합니다.  
  
## <a name="mitigation"></a>완화  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상 버전의 .NET Framework를 대상으로 하고 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 메서드에 의존하여 경우에 따라 멤버 설명자가 동일할 때 `false`를 반환하면 다음 두 가지 해결 방법을 사용할 수 있습니다.  
  
-   app.config 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음을 추가하여 소스 코드를 수정하지 않고 이러한 변경을 옵트아웃(opt out)할 수 있습니다.  
  
    ```xml  
  
    <runtime>  
        <AppContextSwitchOverrides value = "Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />  
     </runtime>  
  
    ```  
  
-   다음 코드 조각과 같이 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 메서드를 호출한 후에 <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> 및 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> 속성을 수동으로 비교하여 이전 동작을 복원하도록 소스 코드를 수정할 수 있습니다.  
  
    ```csharp  
  
    if (memberDescriptor1.Equals(memberDescriptor2) &   
        memberDescriptor1.Description.Equals(memberDescriptor2.Category)) {  
          // Code to execute if true.  
    }  
    else {  
          // Code to execute if false.     
    }  
  
    ```  
  
    ```  
  
    If memberDescriptor1.Equals(memberDescriptor2) And   
        memberDescriptor1.Description.Equals(memberDescriptor2.Category)  
          // Code to execute if True.  
    Else  
          // Code to execute if False.     
    End If  
  
    ```  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 이전 버전을 대상으로 하는 앱의 경우 app.config 파일에 다음 값을 추가하여 이 변경을 사용하도록 설정할 수 있습니다.  
  
```xml  
  
<runtime>  
    \<AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true />  
</runtime>  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)   
 [4.6.2의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
