---
title: s_isDebuggerCheckDisabledForTestPurposes 필드
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
robots: noindex,nofollow
ms.openlocfilehash: fbbd8d33ea163efaad1417ab4a1435df729e4897
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752210"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="1e411-102">s_isDebuggerCheckDisabledForTestPurposes 필드</span><span class="sxs-lookup"><span data-stu-id="1e411-102">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="1e411-103">이 전용 필드에는 `System.Windows.Diagnostics.VisualDiagnostics` 클래스 활성 디버거가 대 한 내부 검사를 수행할지 여부를 확인 하려면 Visual Studio에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e411-103">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="1e411-104">구문</span><span class="sxs-lookup"><span data-stu-id="1e411-104">Syntax</span></span>
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  <span data-ttu-id="1e411-105">API는 `System.Windows.Diagnostics.VisualDiagnostics` 클래스는 응용 프로그램이 디버거에서 실행 중인 경우에 사용할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e411-105">API's in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="1e411-106">설정 `s_isDebuggerCheckDisabledForTestPurposes` 를 `true` Api는 디버거 외부에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e411-106">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>  
>   
>  <span data-ttu-id="1e411-107">Microsoft은 프로덕션 응용 프로그램의 어떤 상황에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e411-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>  

## <a name="requirements"></a><span data-ttu-id="1e411-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e411-108">Requirements</span></span>

<span data-ttu-id="1e411-109">**Namespace:** <xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="1e411-109">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="1e411-110">**어셈블리:** PresentationCore (에: PresentationCore.dll)</span><span class="sxs-lookup"><span data-stu-id="1e411-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="1e411-111">**.NET framework 버전:** 4.6부터 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e411-111">**.NET Framework versions:** Available since 4.6.</span></span>
