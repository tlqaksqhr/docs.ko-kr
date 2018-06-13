---
title: '완화: 포인터 기반 터치 및 스타일러스 지원'
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da7d55b34bc21f0c11f13565d017587b4276bad3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33387782"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="6f065-102">완화: 포인터 기반 터치 및 스타일러스 지원</span><span class="sxs-lookup"><span data-stu-id="6f065-102">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="6f065-103">.NET Framework 4.7을 대상으로 하고 Windows 10 작성자 업데이트 버전 이상의 Windows 시스템에서 실행되는 WPF 응용 프로그램은 선택적 `WM_POINTER` 기반 WPF 터치/스타일러스 스택을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-103">WPF applications that target the .NET Framework 4.7 and are running on Windows Systems starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="6f065-104">영향</span><span class="sxs-lookup"><span data-stu-id="6f065-104">Impact</span></span>

<span data-ttu-id="6f065-105">포인터 기반 터치/스타일러스 지원을 명시적으로 사용하지 않도록 하는 개발자는 WPF 터치/스타일러스 동작이 달라지지 않는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-105">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="6f065-106">다음은 현재 선택적 `WM_POINTER` 기반 터치/스타일러스 스택의 알려진 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-106">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="6f065-107">실시간 잉크 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-107">No support for real-time inking.</span></span>

   <span data-ttu-id="6f065-108">잉크 입력 및 스타일러스 플러그 인은 계속 작동하지만 UI 스레드에서 처리되므로 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-108">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="6f065-109">터치/스타일러스 이벤트에서 마우스 이벤트로 전환하는 방식의 변경으로 인해 동작이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-109">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="6f065-110">조작이 다르게 동작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-110">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="6f065-111">끌어서 놓기 작업이 터치 입력에 대해 적절한 피드백을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-111">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="6f065-112">(이러한 문제가 스타일러스 입력에는 영향을 주지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="6f065-112">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="6f065-113">끌어서 놓기가 더 이상 터치/스타일러스 이벤트에서 시작될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-113">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="6f065-114">이로 인해 마우스 입력이 감지될 때까지 응용 프로그램이 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-114">This can potentially hang the application until mouse input is detected.</span></span> <span data-ttu-id="6f065-115">대신, 개발자는 마우스 이벤트에서 끌어서 놓기를 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-115">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wmpointer-based-touchstylus-support"></a><span data-ttu-id="6f065-116">WM_POINTER 기반 터치/스타일러스 지원 옵트인(opt in)</span><span class="sxs-lookup"><span data-stu-id="6f065-116">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="6f065-117">이 스택을 사용하도록 설정하려는 개발자는 응용 프로그램의 app.config 파일에 다음을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-117">Developers who wish to enable this stack can add the following to their application's app.config file:</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="6f065-118">이 항목을 제거하거나 해당 값을 `false`로 설정하면 이 선택적 스택이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f065-118">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f065-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f065-119">See also</span></span>

[<span data-ttu-id="6f065-120">.NET Framework 4.7.1의 대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="6f065-120">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)
