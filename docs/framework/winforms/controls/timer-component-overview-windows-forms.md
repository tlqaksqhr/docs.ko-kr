---
title: Timer 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 39bc3c8cda06a62eb40b042e46cbd070a82cce01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535504"
---
# <a name="timer-component-overview-windows-forms"></a>Timer 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.Timer>는 일정한 간격마다 이벤트를 발생시키는 구성 요소입니다. 이 구성 요소는 Windows Forms 환경에 맞게 설계되었습니다. 서버 환경에 적합한 타이머가 필요한 경우 [서버 기반 타이머 소개](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)를 참조하세요.  
  
## <a name="key-properties-methods-and-events"></a>키 속성, 메서드 및 이벤트  
 간격의 길이 정의한는 <xref:System.Windows.Forms.Timer.Interval%2A> 속성, 값 (밀리초)입니다. 구성 요소를 사용 하는 경우는 <xref:System.Windows.Forms.Timer.Tick> 이벤트가 간격 마다. 코드 실행을 추가할 위치입니다. 자세한 내용은 참조 [하는 방법: Windows Forms Timer 구성 된 설정 간격 프로시저 실행](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md)합니다. 주요 메서드는 <xref:System.Windows.Forms.Timer> 구성 요소는 <xref:System.Windows.Forms.Timer.Start%2A> 및 <xref:System.Windows.Forms.Timer.Stop%2A>, 타이머를 켜고 끄려면입니다. 타이머 꺼진 다시 설정 합니다. 일시 중지 하는 방법이 있으면는 <xref:System.Windows.Forms.Timer> 구성 요소입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Timer>  
 [Timer 구성 요소](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Windows Forms Timer 구성 요소의 Interval 속성에 대한 제한 사항](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
