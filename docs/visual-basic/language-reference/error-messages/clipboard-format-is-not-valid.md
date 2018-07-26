---
title: 클립보드 형식이 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: f2a0ab33c1749117d5de4987e85c44602ccd29ce
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245560"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="3b4db-102">클립보드 형식이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4db-102">Clipboard format is not valid</span></span>
<span data-ttu-id="3b4db-103">지정된 된 클립보드 형식 실행 중인 메서드를 사용 하 여 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4db-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="3b4db-104">이 오류에 대 한 가능한 원인 중:</span><span class="sxs-lookup"><span data-stu-id="3b4db-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="3b4db-105">클립보드의를 사용 하 여 `GetText` 또는 `SetText` 이외의 다른 클립보드 형식 사용 하 여 메서드 `vbCFText` 또는 `vbCFLink`합니다.</span><span class="sxs-lookup"><span data-stu-id="3b4db-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="3b4db-106">클립보드의를 사용 하 여 `GetData` 또는 `SetData` 이외의 다른 클립보드 형식 사용 하 여 메서드 `vbCFBitmap`를 `vbCFDIB`, 또는 `vbCFMetafile`합니다.</span><span class="sxs-lookup"><span data-stu-id="3b4db-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="3b4db-107">사용 하는 `GetData` 또는 `SetData` 의 메서드는 `DataObject` 등록 된 형식 (HC000-& HFFFF), Microsoft Windows에서 예약 된 범위에서를 클립보드 형식으로 때 해당 클립보드 형식을 등록 되지 않은 Microsoft Windows를 사용 하 여 .</span><span class="sxs-lookup"><span data-stu-id="3b4db-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3b4db-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3b4db-108">To correct this error</span></span>  
  
-   <span data-ttu-id="3b4db-109">잘못 된 형식을 제거 하 고 유효한을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b4db-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b4db-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b4db-110">See Also</span></span>  
 [<span data-ttu-id="3b4db-111">클립보드: 기타 서식 추가</span><span class="sxs-lookup"><span data-stu-id="3b4db-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
