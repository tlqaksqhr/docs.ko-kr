---
title: 클립보드 형식이 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: eef16096b269902dbaca6a344abf4c5f6a504fb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586223"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="27662-102">클립보드 형식이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27662-102">Clipboard format is not valid</span></span>
<span data-ttu-id="27662-103">지정 된 클립보드 형식을 실행 중인 메서드의와 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27662-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="27662-104">이 오류의 가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="27662-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="27662-105">클립보드의를 사용 하 여 `GetText` 또는 `SetText` 메서드 이외의 클립보드 형식으로 `vbCFText` 또는 `vbCFLink`합니다.</span><span class="sxs-lookup"><span data-stu-id="27662-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="27662-106">클립보드의를 사용 하 여 `GetData` 또는 `SetData` 메서드 이외의 클립보드 형식으로 `vbCFBitmap`, `vbCFDIB`, 또는 `vbCFMetafile`합니다.</span><span class="sxs-lookup"><span data-stu-id="27662-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="27662-107">사용 하는 `DataObject``GetData` 메서드 또는 `SetData` 메서드 등록 된 형식 (HC000-& HFFFF), Microsoft Windows에서 예약 범위에서 클립보드 형식으로 때 해당 클립보드 형식을 등록 되지 않은 Microsoft Windows와 함께 합니다.</span><span class="sxs-lookup"><span data-stu-id="27662-107">Using the `DataObject``GetData` method or `SetData` method with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="27662-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="27662-108">To correct this error</span></span>  
  
-   <span data-ttu-id="27662-109">잘못 된 형식을 제거 하 고 올바른을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27662-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27662-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27662-110">See Also</span></span>  
 [<span data-ttu-id="27662-111">클립보드: 기타 서식 추가</span><span class="sxs-lookup"><span data-stu-id="27662-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
