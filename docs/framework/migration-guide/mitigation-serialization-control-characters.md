---
title: "완화: DataContractJsonSerializer로 제어 문자 serialization"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6da580d208736a64e2094f701fb4c1241a488322
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a><span data-ttu-id="ab297-102">완화: DataContractJsonSerializer로 제어 문자 serialization</span><span class="sxs-lookup"><span data-stu-id="ab297-102">Mitigation: Serialization of Control Characters with the DataContractJsonSerializer</span></span>

<span data-ttu-id="ab297-103">.NET Framework 4.7부터 제어 문자가 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>로 serialize되는 방식이 ECMAScript V6 및 V8에 맞게 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab297-103">Starting with the .NET Framework 4.7, the way in which control characters are serialized with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> has changed to conform to ECMAScript V6 and V8.</span></span> 
 
## <a name="impact"></a><span data-ttu-id="ab297-104">영향</span><span class="sxs-lookup"><span data-stu-id="ab297-104">Impact</span></span>

<span data-ttu-id="ab297-105">.NET framework 4.6.2 이하 버전에서는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>가 ECMAScript V6 및 V8 표준과 호환되는 방식으로 `\b`, `\f`, `\t` 등의 일부 특수 제어 문자를 serialize하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="ab297-105">In the .NET framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> did not serialize some special control characters, such as `\b`, `\f`, and `\t`, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span>

<span data-ttu-id="ab297-106">.NET Framework 4.7 이상의 .NET Framework 버전을 대상으로 하는 앱의 경우 이러한 제어 문자의 serialization이 ECMAScript V6 및 V8과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab297-106">For apps that target versions of the .NET Framework starting with the .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span> <span data-ttu-id="ab297-107">다음 API가 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ab297-107">The following APIs are affected:</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a><span data-ttu-id="ab297-108">완화</span><span class="sxs-lookup"><span data-stu-id="ab297-108">Mitigation</span></span>

<span data-ttu-id="ab297-109">.NET Framework 4.7 이상의 .NET Framework 버전을 대상으로 하는 앱의 경우 이 동작이 기본적으로 사용되도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab297-109">For apps that target versions of the .NET Framework starting with the .NET Framework 4.7, this behavior is enabled by default.</span></span>

<span data-ttu-id="ab297-110">이 동작을 원치 않는 경우 app.config 또는 web.config 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 이 기능을 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab297-110">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a><span data-ttu-id="ab297-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab297-111">See also</span></span>
[<span data-ttu-id="ab297-112">.NET Framework 4.7.1의 대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="ab297-112">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

