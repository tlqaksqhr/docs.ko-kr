---
title: Async 응용 프로그램 미세 조정(C#)
ms.date: 07/20/2015
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
ms.openlocfilehash: cf4e0082fbaa2a5189646014e53f0320e16f40de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fine-tuning-your-async-application-c"></a>Async 응용 프로그램 미세 조정(C#)
<xref:System.Threading.Tasks.Task> 형식이 제공하는 메서드 및 속성을 사용하여 async 응용 프로그램에 정확성 및 유연성을 추가할 수 있습니다. 이 섹션의 항목에서는 <xref:System.Threading.CancellationToken>을 사용하는 예제와 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>과 같은 중요한 `Task` 메서드를 보여 줍니다.  
  
 `WhenAny` 및 `WhenAll`를 사용하면 더 쉽게 여러 작업을 시작하고 단일 작업을 모니터링하여 완료할 때까지 기다릴 수 있습니다.  
  
-   `WhenAny`는 컬렉션의 임의 작업이 완료되면 완료되는 작업을 반환합니다.  
  
     `WhenAny`를 사용하는 예제는 [비동기 작업 하나가 완료되면 남은 비동기 작업 취소(C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) 및 [S비동기 작업을 여러 개 시작하고 완료될 때마다 처리(C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)를 참조하세요.  
  
-   `WhenAll`은 컬렉션의 모든 작업이 완료되면 완료되는 작업을 반환합니다.  
  
     자세한 내용 및 `WhenAll`을 사용하는 예제는 [방법: Task.WhenAll을 사용하여 비동기 연습 확장(C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)을 참조하세요.  
  
 이 섹션에 포함된 예제는 다음과 같습니다.  
  
-   [비동기 작업 또는 작업 목록 취소(C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)  
  
-   [일정 기간 이후 비동기 작업 취소(C#)](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [비동기 작업 하나가 완료되면 남은 비동기 작업 취소(C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [비동기 작업을 여러 개 시작하고 완료될 때마다 처리(C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.  
  
 다음 그림과 같이 프로젝트는 프로세스를 시작하는 단추와 프로세스를 취소하는 단추가 포함된 UI를 만듭니다. 단추 이름은 `startButton` 및 `cancelButton`입니다.  
  
 ![취소 단추가 있는 WPF 창](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "취소")  
  
 [Async 샘플: 응용 프로그램 세부 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 전체 WPF(Windows Presentation Foundation) 프로젝트를 다운로드하여 완료할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [async 및 await를 사용한 비동기 프로그래밍(C#)](../../../../csharp/programming-guide/concepts/async/index.md)
