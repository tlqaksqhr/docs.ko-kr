---
title: MSMQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e72d3e400440b830b689f476753a7c8c40fe2586
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="msmq"></a>MSMQ
MSMQ 응용 프로그램에서는 대기 중인 채널에서 MSMQ로, 그리고 MSMQ에서 대기 중인 채널로 추가 동작이 전송되지 않습니다.  
  
 또한 보내기 작업에서 MSMQ 메시지 ID와 SOAP 메시지 ID(있는 경우 동작 ID와 함께)가 대기 중인 채널 추적의 일부로 추적됩니다.  
  
 받기 작업에서 MSMQ 메시지 ID와 SOAP 메시지 ID(있는 경우 동작 ID와 함께)가 대기 중인 채널 추적의 일부로 추적됩니다.  
  
 받기 작업에서 필요한 전송은 다른 모든 전송과 유사하게 실행됩니다(바이트 수신->메시지 처리-> 작업).
