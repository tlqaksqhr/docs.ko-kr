---
title: "BackgroundWorker 구성 요소 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords: BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2e49c9c3a8f2b133337ee3c153841a7daeff178
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="backgroundworker-component-overview"></a>BackgroundWorker 구성 요소 개요
일반적으로 수행하는 작업 중에는 실행 시간이 오래 걸릴 수 있는 것들이 많습니다. 예를 들면 다음과 같습니다.  
  
-   이미지 다운로드  
  
-   웹 서비스 호출  
  
-   파일 다운로드 및 업로드(피어 투 피어 응용 프로그램용 파일 포함)  
  
-   복잡한 로컬 계산  
  
-   데이터베이스 트랜잭션  
  
-   로컬 디스크 액세스(메모리 액세스에 비해 속도가 느림)  
  
 이러한 작업을 수행하는 동안에는 사용자 인터페이스가 응답하지 않을 수 있습니다. 응답성이 뛰어난 UI가 필요한데 이러한 작업과 관련하여 지연이 길어지는 경우 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용하면 문제를 편리하게 해결할 수 있습니다.  
  
 <xref:System.ComponentModel.BackgroundWorker> 구성 요소는 응용 프로그램의 주 UI 스레드와는 다른 스레드에서 시간이 많이 걸리는 작업을 "백그라운드"에서 비동기식으로 실행하는 기능을 제공합니다. <xref:System.ComponentModel.BackgroundWorker>를 사용하려는 경우 백그라운드에서 실행하려는 시간이 많이 걸리는 작업자 프로세스를 지정한 다음 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 메서드만 호출하면 됩니다. 호출 스레드는 계속 정상적으로 실행되며 작업자 메서드는 비동기식으로 실행됩니다. 메서드가 완료되면 <xref:System.ComponentModel.BackgroundWorker>는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트를 발생시켜 호출 스레드에 경고를 표시합니다. 이 이벤트는 필요에 따라 작업 결과를 포함합니다.  
  
 <xref:System.ComponentModel.BackgroundWorker> 구성 요소는에서 사용할 수는 **도구 상자**에 **구성 요소** 탭 합니다. 폼에 <xref:System.ComponentModel.BackgroundWorker>를 추가하려면 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 폼으로 끌어 옵니다. 구성 요소 트레이에 표시 되 고 해당 속성이 표시에 **속성** 창.  
  
 비동기 작업을 시작하려면 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 메서드를 사용합니다. <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>는 작업자 메서드로 인수를 전달하는 데 사용할 수 있는 선택적 `object` 매개 변수를 사용합니다. <xref:System.ComponentModel.BackgroundWorker> 클래스는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트를 표시하며, 작업자 스레드는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기를 통해 이 이벤트에 연결됩니다.  
  
 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기는 <xref:System.ComponentModel.DoWorkEventArgs> 속성을 포함하는 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> 매개 변수를 사용합니다. 이 속성은 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>에서 매개 변수를 받으며 작업자 메서드로 전달될 수 있습니다. 이 작업자 메서드는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기에서 호출됩니다. 다음 예에서는 `ComputeFibonacci`라는 작업자 메서드에서 결과를 할당하는 방법을 보여줍니다. 찾을 수 있습니다는 보다 큰 예제의의 일부인 [하는 방법: 백그라운드 작업을 사용 하는 폼 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)합니다.  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 이벤트 처리기를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [이벤트](../../../../docs/standard/events/index.md)합니다.  
  
> [!CAUTION]
>  모든 종류의 다중 스레딩을 사용할 때는 매우 심각하고 복잡한 버그에 잠재적으로 노출됩니다. 다중 스레딩을 사용하는 솔루션을 구현하기 전에 [관리되는 스레딩을 구현하는 최선의 방법](../../../../docs/standard/threading/managed-threading-best-practices.md)을 참조하세요.  
  
 사용 하 여 대 한 자세한 내용은 <xref:System.ComponentModel.BackgroundWorker> 클래스를 참조 하십시오. [하는 방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [빌드에 없음: Visual Basic의 다중 스레딩](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)  
 [방법: 배경 작업을 사용하는 양식 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
