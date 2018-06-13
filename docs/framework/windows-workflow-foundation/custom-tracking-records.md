---
title: 사용자 지정 추적 레코드
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: 6c68c08e5beacee30b517bf0c2bad3e83785409b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511337"
---
# <a name="custom-tracking-records"></a><span data-ttu-id="51512-102">사용자 지정 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="51512-102">Custom Tracking Records</span></span>
<span data-ttu-id="51512-103">이 항목에서는 사용자 지정 추적 레코드를 만들고 이 레코드와 함께 내보내질 데이터로 이 레코드를 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51512-103">This topic demonstrates how to create custom tracking records and populate them with data to be emitted along with the records.</span></span>  
  
## <a name="emitting-custom-tracking-records"></a><span data-ttu-id="51512-104">사용자 지정 추적 레코드 내보내기</span><span class="sxs-lookup"><span data-stu-id="51512-104">Emitting Custom Tracking Records</span></span>  
 <span data-ttu-id="51512-105">다음 예제에 표시된 것처럼 코드 활동에서 사용자 지정 추적 레코드를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51512-105">Custom tracking records can be emitted from a code activity as shown in the following example.</span></span>  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
…  
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");  
            customRecord.Data.Add("SendTime", sendTime);  
            context.Track(customRecord);  
}  
```  
  
 <span data-ttu-id="51512-106"><xref:System.Activities.Tracking.CustomTrackingRecord>에서 <xref:System.Activities.NativeActivityContext.Track%2A> 메서드를 호출하여 코드 활동에서 `ActvityContext`를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="51512-106">A <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted in a code activity by invoking the <xref:System.Activities.NativeActivityContext.Track%2A> method on the `ActvityContext`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51512-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51512-107">See Also</span></span>  
 [<span data-ttu-id="51512-108">Windows Server App Fabric 모니터링</span><span class="sxs-lookup"><span data-stu-id="51512-108">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="51512-109">App Fabric로 응용 프로그램 모니터링</span><span class="sxs-lookup"><span data-stu-id="51512-109">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
