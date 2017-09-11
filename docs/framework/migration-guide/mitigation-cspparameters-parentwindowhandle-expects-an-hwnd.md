---
title: "완화: CspParameters.ParentWindowHandle에 HWND 필요"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- CspParameters.ParentWindowHandle
- CspParameters.ParentWindowHandle retargeting change
ms.assetid: 33264333-71d6-4d43-8827-9c98878cfea7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1b65aaf7149ca29b2af3efdf44ee9489a04c73a2
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-cspparametersparentwindowhandle-expects-an-hwnd"></a><span data-ttu-id="a0172-102">완화: CspParameters.ParentWindowHandle에 HWND 필요</span><span class="sxs-lookup"><span data-stu-id="a0172-102">Mitigation: CspParameters.ParentWindowHandle Expects an HWND</span></span>

<span data-ttu-id="a0172-103">.NET Framework 2.0에 도입된 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> 속성을 사용하면 응용 프로그램에서 키에 액세스하는 데 필요한 UI(PIN 프롬프트 또는 동의 대화 상자)가 지정된 창에 대한 모달 자식 항목으로 열리도록 부모 창 핸들 값을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0172-103">The <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property, introduced in the .NET Framework 2.0, allows an application to register a parent window handle value such that any UI required to access the key (such as a PIN prompt or a consent dialog) opens as a modal child to the specified window.</span></span> <span data-ttu-id="a0172-104">.NET Framework 4.7을 대상으로 하는 응용 프로그램부터, 창 핸들(HWND)을 이 속성에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0172-104">Starting with applications that target the .NET Framework 4.7, a window handle (HWND) can be assigned to this property.</span></span>

<span data-ttu-id="a0172-105">.NET Framework 4.6.2 이하 버전에서 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> 속성에 할당된 값은 메모리에서 HWND 값의 위치를 나타내는 <xref:System.IntPtr>로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0172-105">In versions of the .NET Framework through the .NET Framework 4.6.2, the value assigned to the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property was expected to be an <xref:System.IntPtr> that represents the location in memory where the HWND value resided.</span></span> <span data-ttu-id="a0172-106">Windows 7 및 이전 버전의 Windows 운영 체제에서는 이 속성을 `form.Handle`로 설정해도 아무 영향이 없지만, Windows 8 이상 버전에서는 “매개 변수가 잘못되었습니다.”라는 메시지와 함께 <xref:System.Security.Cryptography>가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0172-106">On Windows 7 and earlier versions of the Windows operating system, setting the property to `form.Handle` had no effect, but on Windows 8 and later versions, it results in a <xref:System.Security.Cryptography> with the message, "The parameter is incorrect."</span></span>

<span data-ttu-id="a0172-107">.NET Framework 4.7을 대상으로 하는 앱부터 다음과 같은 코드를 사용하여 Windows Forms 응용 프로그램에서 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0172-107">Starting with apps that target the .NET Framework 4.7, a Windows Forms application can set the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property with code like the following:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="impact"></a><span data-ttu-id="a0172-108">영향</span><span class="sxs-lookup"><span data-stu-id="a0172-108">Impact</span></span>

<span data-ttu-id="a0172-109">부모 창 관계를 등록하려는 .NET Framework 4.7 이상을 대상으로 하는 응용 프로그램에서는 다음과 같은 간단한 형식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a0172-109">Applications targeting the .NET Framework 4.7 or later that wish to register a parent window relationship are encouraged to use the simplified form:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="mitigation"></a><span data-ttu-id="a0172-110">완화</span><span class="sxs-lookup"><span data-stu-id="a0172-110">Mitigation</span></span>

<span data-ttu-id="a0172-111">올바른 값이 `form.Handle` 값을 포함하는 메모리 위치의 주소임을 확인한 개발자는 <xref:System.AppContext> 스위치 `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle`을 `true`로 설정하여 이러한 동작 변경을 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0172-111">Developers who had identified that the correct value was the address of the memory location that held the `form.Handle` value can opt out of this change in behavior by setting the <xref:System.AppContext> switch `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` to `true`:</span></span>

- <span data-ttu-id="a0172-112"><xref:System.AppContext> 인스턴스에서 호환성 스위치를 프로그래밍 방식으로 설정</span><span class="sxs-lookup"><span data-stu-id="a0172-112">By programmatically setting compatibility switches on the <xref:System.AppContext> instance.</span></span>

- <span data-ttu-id="a0172-113">다음 줄을 app.config 파일의 `<runtime>` 섹션에 추가</span><span class="sxs-lookup"><span data-stu-id="a0172-113">By adding the following line to the `<runtime>` section of the app.config file:</span></span>
   
   ```xml
   <runtime>
     <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
   </runtime>
   ```

<span data-ttu-id="a0172-114">반대로 .NET Framework 4.7에서 실행되지만 이전 버전의 .NET Framework를 대상으로 하는 응용 프로그램에 대한 새로운 동작을 옵트인(opt in)하려는 사용자는 <xref:System.AppContext> 스위치를 `false`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0172-114">Conversely, users who wish to opt in to the new behavior for applications that run under the .NET Framework 4.7 but target an earlier version of the .NET Framework versions can set the <xref:System.AppContext> switch to `false`.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="a0172-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0172-115">See also</span></span>

[<span data-ttu-id="a0172-116">.NET Framework 4.7.1의 대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="a0172-116">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

