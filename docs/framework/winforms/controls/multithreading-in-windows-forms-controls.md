---
title: Windows Forms 컨트롤의 다중 스레딩
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 68822c62a1a195ce3128d51c765cfeba2056955d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="multithreading-in-windows-forms-controls"></a>Windows Forms 컨트롤의 다중 스레딩
대부분의 응용 프로그램을 만들면 사용자 인터페이스 (UI) 응답성 다른 스레드에서 시간이 많이 걸리는 작업을 수행 하 여 됩니다. 여러 가지 도구에 사용할 수 있는 다중 스레딩을 포함 하 여 Windows Forms 컨트롤은 <xref:System.Threading> 네임 스페이스는 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 메서드를 및 `BackgroundWorker` 구성 요소입니다.  
  
> [!NOTE]
>  `BackgroundWorker` 대체 하 고 기능을 추가 하는 구성 요소는 <xref:System.Threading> 네임 스페이스 및 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 메서드도 있습니다; 그러나 이러한 됩니다 유지의 이전 버전과 호환성 및 이후 사용 하도록 선택할 수 있습니다. 자세한 내용은 참조 [BackgroundWorker 구성 요소 개요](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 스레드로부터 안전한 방식으로 Windows Forms 컨트롤 호출](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Windows Forms 컨트롤에 스레드로부터 안전한 호출을 수행 하는 방법을 보여 줍니다.  
  
 [방법: 백그라운드 스레드를 사용하여 파일 검색](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 사용 하는 방법을 보여 줍니다.는 <xref:System.Threading> 네임 스페이스 및 <xref:System.Windows.Forms.Control.BeginInvoke%2A> 메서드를 비동기적으로 파일을 검색 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ComponentModel.BackgroundWorker>  
 비동기 작업에 대 한 작업자 스레드를 캡슐화 하는 구성 요소에 설명 합니다.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 비동기적으로 소리를 로드 하는 방법에 설명 합니다.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 이미지를 비동기적으로 로드 하는 방법에 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 시간이 많이 걸리는 작업을 수행 하는 방법을 보여 줍니다.는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소입니다.  
  
 [BackgroundWorker 구성 요소 개요](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 사용 하는 방법을 설명 하는 항목을 제공 된 <xref:System.ComponentModel.BackgroundWorker> 비동기 작업에 대 한 구성 요소입니다.
