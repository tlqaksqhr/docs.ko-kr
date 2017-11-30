---
title: "EventLogSource에 지정된 소스 이름이 EventLogName에 지정된 로그가 아닌 로그에 등록되었습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c190caa7634760c2e4dc4a2bb7a9a09f532eb0ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a><span data-ttu-id="4f953-102">EventLogSource에 지정된 소스 이름이 EventLogName에 지정된 로그가 아닌 로그에 등록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f953-102">Source name specified in EventLogSource is registered to a log other than that specified in EventLogName</span></span>
<span data-ttu-id="4f953-103">`EventLog` 에서 다른 로그에 등록된 소스를 참조하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f953-103">The `EventLog` is attempting to refer to a source that is registered to a different log.</span></span> <span data-ttu-id="4f953-104">이벤트 로그에 항목을 쓰는 경우 <xref:System.Diagnostics.EventLog.Source%2A> 속성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f953-104">If you are writing entries to an event log, you must specify the <xref:System.Diagnostics.EventLog.Source%2A> property.</span></span> <span data-ttu-id="4f953-105"><xref:System.Diagnostics.EventLog.Source%2A> 속성은 구성 요소를 항목의 유효한 소스로 이벤트 로그에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4f953-105">The <xref:System.Diagnostics.EventLog.Source%2A> property registers your component with the event log as a valid source of entries.</span></span> <span data-ttu-id="4f953-106">단일 소스는 한 번에 하나의 이벤트 로그에만 연결되고 항목을 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f953-106">A single source can be associated with (and therefore write entries to) only one event log at a time.</span></span>  
  
 <span data-ttu-id="4f953-107">기본적으로 구성 요소를 유효한 소스로 먼저 등록하지 않고 항목을 쓰려고 하면 시스템이 자동으로 <xref:System.Diagnostics.EventLog.Source%2A> 속성의 값을 소스 문자열로 사용하여 이벤트 로그에 소스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4f953-107">By default, if you try to write an entry without first having registered your component as a valid source, the system automatically registers the source with the event log, using the value of the <xref:System.Diagnostics.EventLog.Source%2A> property as the source string.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4f953-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="4f953-108">To correct this error</span></span>  
  
-   <span data-ttu-id="4f953-109">소스가 올바른 로그에 등록되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4f953-109">Make sure the source is registered to the correct log.</span></span> <span data-ttu-id="4f953-110">이렇게 하려면 <xref:System.Diagnostics.EventLog.CreateEventSource%2A> 메서드 또는 해당 오버로드 중 하나를 사용하여 이벤트 로그에 구성 요소를 고유하게 식별하는 문자열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f953-110">To do this, use the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method or one of its overloads to specify a string that uniquely identifies your component to the event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f953-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f953-111">See Also</span></span>  
 [<span data-ttu-id="4f953-112">이벤트 로그 관리</span><span class="sxs-lookup"><span data-stu-id="4f953-112">Administering Event Logs</span></span>](http://msdn.microsoft.com/en-us/35f53238-bdd2-417b-acd8-2fd9f7397f18)  
 [<span data-ttu-id="4f953-113">이벤트 로그 참조</span><span class="sxs-lookup"><span data-stu-id="4f953-113">Event Log References</span></span>](http://msdn.microsoft.com/en-us/4af0661c-6c96-49f4-961d-b26ed9bc3e87)  
 [<span data-ttu-id="4f953-114">방법: 응용 프로그램 이벤트 로그 항목의 원본으로 추가</span><span class="sxs-lookup"><span data-stu-id="4f953-114">How to: Add Your Application as a Source of Event Log Entries</span></span>](http://msdn.microsoft.com/en-us/948ff920-a739-4e66-a191-ee951512d42c)  
 [<span data-ttu-id="4f953-115">방법: 이벤트 소스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f953-115">How to: Remove an Event Source</span></span>](http://msdn.microsoft.com/en-us/bc66c900-4b8a-426a-b8e2-17031a20167e)
