---
title: "완화: MemberDescriptor.Equals"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4989d3c2611b500063158955f102931902e1ab32
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-memberdescriptorequals"></a><span data-ttu-id="f3cb3-102">완화: MemberDescriptor.Equals</span><span class="sxs-lookup"><span data-stu-id="f3cb3-102">Mitigation: MemberDescriptor.Equals</span></span>
<span data-ttu-id="f3cb3-103">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 메서드의 구현이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cb3-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method has changed.</span></span> <span data-ttu-id="f3cb3-104">`System.ComponentModel.EventDescriptor.Equals` 및 `System.ComponentModel.PropertyDescriptor.Equals` 메서드는 기본 클래스 구현을 상속하므로 이러한 변경 내용이 이러한 메서드에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3cb3-104">Because the `System.ComponentModel.EventDescriptor.Equals` and  `System.ComponentModel.PropertyDescriptor.Equals` methods inherit the base class implementation, the change also affects these methods.</span></span>  
  
 <span data-ttu-id="f3cb3-105">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이전에 .NET Framework 버전을 대상으로 하는 앱에서는 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 메서드의 같음 테스트 중 일부가 한 개체의 <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> 속성과 다른 개체의 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> 속성을 올바르지 않게 비교했습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cb3-105">In apps that target versions of the .NET Framework prior to [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a portion of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method's test for equality  incorrectly compared the <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> property of one object with the <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> property of the other.</span></span> <span data-ttu-id="f3cb3-106">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 메서드는 두 개체의 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> 속성을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cb3-106">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method compares the <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> property of the two objects.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="f3cb3-107">영향</span><span class="sxs-lookup"><span data-stu-id="f3cb3-107">Impact</span></span>  
 <span data-ttu-id="f3cb3-108">이 변경 내용은 <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> 개체에 대한 같음 테스트를 올바르게 구현하여 영향을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="f3cb3-108">This change correctly implements the test for equality for <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> objects and should have minimal impact.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="f3cb3-109">완화</span><span class="sxs-lookup"><span data-stu-id="f3cb3-109">Mitigation</span></span>  
 <span data-ttu-id="f3cb3-110">앱이 .NET Framework의 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 또는 이후 버전을 대상으로 하며 멤버 설명자가 같을 때 더러 `false`를 반환하는 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 메서드에 의존하는 경우, 두 가지 해결 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cb3-110">Two workarounds are available if your app targets the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or a later version of the .NET Framework and it depends on the  <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method sometimes returning `false` when member descriptors are equivalent:</span></span>  
  
-   <span data-ttu-id="f3cb3-111">app.config 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음을 추가하여 소스 코드를 수정하지 않고 이러한 변경을 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cb3-111">You can opt out of this change without modifying your source code by adding the following to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value = "Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />  
     </runtime>  
    ```  
  
-   <span data-ttu-id="f3cb3-112">다음 코드 조각에서처럼 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> 메서드를 호출한 후 <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> 및 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> 속성을 수동으로 비교함으로써 소스 코드를 수정하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cb3-112">You can modify your source code to restore the previous behavior by manually comparing the  <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> and <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> properties after calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method, as the following code fragment does.</span></span>  
  
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
  
 <span data-ttu-id="f3cb3-113">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 이전 버전을 대상으로 하는 앱의 경우 app.config 파일에 다음 값을 추가하여 이 변경을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3cb3-113">For apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, you can enable this change by adding the following value to your app.config file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3cb3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3cb3-114">See Also</span></span>  
 <span data-ttu-id="f3cb3-115">[대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md) </span><span class="sxs-lookup"><span data-stu-id="f3cb3-115">[Retargeting Changes](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md) </span></span>  
 [<span data-ttu-id="f3cb3-116">4.6.2의 응용 프로그램 호환성</span><span class="sxs-lookup"><span data-stu-id="f3cb3-116">Application Compatibility in 4.6.2</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)

