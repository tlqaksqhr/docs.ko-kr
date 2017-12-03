---
title: "비동기 작업에서 오류 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a7c23dec2f92ed8654d5f0460966dc19af0a8405
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="error-handling-in-asynchronous-activities"></a><span data-ttu-id="4de44-102">비동기 작업에서 오류 처리</span><span class="sxs-lookup"><span data-stu-id="4de44-102">Error handling in asynchronous activities</span></span>
<span data-ttu-id="4de44-103"><xref:System.Activities.AsyncCodeActivity>에서 오류 처리를 제공하면 활동의 콜백 시스템을 통해 오류를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4de44-103">Providing error handling in an <xref:System.Activities.AsyncCodeActivity> involves routing the error through the activity’s callback system.</span></span> <span data-ttu-id="4de44-104">이 항목은 SendMail 활동 샘플을 사용하여 호스트에 비동기 작업에서 throw되는 오류가 발생하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4de44-104">This topic describes how to get an error that is thrown in an asynchronous operation back to the host, using the SendMail activity sample.</span></span>  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a><span data-ttu-id="4de44-105">호스트에 비동기 활동에서 throw되는 오류 반환</span><span class="sxs-lookup"><span data-stu-id="4de44-105">Returning an error thrown in an asynchronous activity back to the host</span></span>  
 <span data-ttu-id="4de44-106">SendMail 활동 샘플에서 호스트에 비동기 작업의 오류를 라우팅하는 것은 다음 단계를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4de44-106">Routing an error in an asynchronous operation back to the host in the SendMail activity sample involves the following steps:</span></span>  
  
-   <span data-ttu-id="4de44-107">`SendMailAsyncResult` 클래스에 예외 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4de44-107">Add an Exception property to the `SendMailAsyncResult` class.</span></span>  
  
-   <span data-ttu-id="4de44-108">`SendCompleted` 이벤트 처리기에서 해당 속성에 throw된 오류를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4de44-108">Copy the thrown error to that property in the `SendCompleted` event handler.</span></span>  
  
-   <span data-ttu-id="4de44-109">`EndExecute` 이벤트 처리기에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="4de44-109">Throw the exception in the `EndExecute` event handler.</span></span>  
  
 <span data-ttu-id="4de44-110">결과 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4de44-110">The resulting code is as follows.</span></span>  
  
```csharp  
class SendMailAsyncResult : IAsyncResult  
        {  
            …  
            public Exception Error { get; set; }   
            …  
            void SendCompleted(object sender, AsyncCompletedEventArgs e)  
            {  
                Error = e.Error;  
                this.asyncWaitHandle.Set();  
                callback(this);  
            }  
         }  
  
    public sealed class SendMail: AsyncCodeActivity  
    {  
         …  
        protected override void EndExecute(AsyncCodeActivityContext context, IAsyncResult result)  
        {  
            SendMailAsyncResult sendMailResult = result as SendMailAsyncResult;  
            if (sendMailResult != null && sendMailResult.Error != null)  
                throw sendMailResult.Error;   
        }  
    }  
```
