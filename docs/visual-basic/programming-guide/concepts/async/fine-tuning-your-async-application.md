---
title: "Async (Visual Basic) 응용 프로그램을 미세 조정 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7d0cac2fe7305031b93a375a08e785285a291320
ms.lasthandoff: 03/13/2017

---
# <a name="fine-tuning-your-async-application-visual-basic"></a>Async (Visual Basic) 응용 프로그램을 미세 조정
추가할 수 있습니다 정밀도 및 유연성을 비동기 응용 프로그램에 메서드 및 속성을 사용 하 여 하는 <xref:System.Threading.Tasks.Task>형식을 사용할 수 있도록 합니다.</xref:System.Threading.Tasks.Task> 이 섹션의 항목 사용 하는 예제를 보여 줍니다. <xref:System.Threading.CancellationToken>중요 한 `Task` <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> </xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> 등의</xref:System.Threading.CancellationToken>  
  
 사용 하 여 `WhenAny` 및 `WhenAll`를 더 쉽게 여러 작업을 시작 하 고 단일 작업을 모니터링 하 여 완료를 기다리는 수 있습니다.  
  
-   `WhenAny`컬렉션에서 모든 작업이 완료 되 면 완료 되는 작업을 반환 합니다.  
  
     사용 하는 예제를 보려면 `WhenAny`, 참조 [하나의 완전 (Visual Basic) 한 후 남은 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)및 [여러 비동기 작업을 시작 하 고 프로세스에로 이러한 완전 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)합니다.  
  
-   `WhenAll`컬렉션의 모든 작업이 완료 되 면 완료 하는 작업을 반환 합니다.  
  
     자세한 내용 및 사용 하는 예제 `WhenAll`, 참조 [하는 방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)합니다.  
  
 이 섹션에는 다음 예제에서는 포함 되어 있습니다.  
  
-   [비동기 작업 또는 작업 (Visual Basic) 목록이 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)합니다.  
  
-   [(Visual Basic) 기간 이후 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [하나가 (Visual Basic) 완료 되 면 남은 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [여러 비동기 작업을 시작 하 고 (Visual Basic) 완료 될 때마다 처리](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.  
  
 프로젝트는 프로세스를 시작 하는 단추와 다음 이미지와 같이, 취소 하는 단추가 포함 된 UI를 만듭니다. 단추는 이름이 지정 `startButton` 및 `cancelButton`합니다.  
  
 ![취소 단추가 있는 WPF 창](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "취소")  
  
 전체 Windows Presentation Foundation (WPF) 프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
