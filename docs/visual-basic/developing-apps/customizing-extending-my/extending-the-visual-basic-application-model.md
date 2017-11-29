---
title: "Visual Basic 응용 프로그램 모델 확장"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 15e6ea1a8b2df0b8ed1b84abceee9e6be2c556f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="extending-the-visual-basic-application-model"></a>Visual Basic 응용 프로그램 모델 확장
재정의 하 여 응용 프로그램 모델에 기능을 추가할 수 있습니다는 `Overridable` 의 멤버는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스입니다. 이 기법을 사용 하면 응용 프로그램이 시작 되 고 종료 하는 대로 사용자 고유의 메서드 호출을 추가 하 고 응용 프로그램 모델의 동작을 사용자 지정할 수 있습니다.  
  
## <a name="visual-overview-of-the-application-model"></a>응용 프로그램 모델의 시각적 개요  
 이 섹션은 시각적으로 Visual Basic 응용 프로그램 모델에는 함수 호출 시퀀스를 표시합니다. 다음 섹션 자세히 함수의 용도 설명합니다.  
  
 다음 그래픽 일반 Visual Basic Windows Forms 응용 프로그램에서 응용 프로그램 모델 호출 시퀀스를 보여 줍니다. 시퀀스를 시작 하는 경우는 `Sub Main` 프로시저 호출에서 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 메서드.  
  
 ![Visual Basic 응용 프로그램 모델 &#45; &#45; 실행](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelrun.gif "VB_ModelRun")  
  
 Visual Basic 응용 프로그램 모델 제공의 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 및 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 이벤트입니다. 다음 그래픽은 이러한 이벤트를 발생 시키기 위한 메커니즘을 보여 줍니다.  
  
 ![Visual Basic 응용 프로그램 모델 &#45; &#45; 다음 인스턴스](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelnext.gif "VB_ModelNext")  
  
 ![Visual Basic 응용 프로그램 모델 처리 되지 않은 예외가](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_unhandex.gif "VB_UnhandEx")  
  
## <a name="overriding-the-base-methods"></a>기본 메서드 재정의  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 는 순서를 정의 하는 메서드는 `Application` 메서드를 실행 합니다. 기본적으로는 `Sub Main` 을 호출 하는 Windows Forms 응용 프로그램에 대 한 프로시저는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 메서드.  
  
 응용 프로그램이 있는 경우 일반 응용 프로그램 (다중 인스턴스 응용 프로그램) 또는 단일 인스턴스 응용 프로그램의 첫 번째 인스턴스는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 메서드가 실행 되는 `Overridable` 다음과 같은 순서로 메서드:  
  
1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>. 기본적으로이 메서드 비주얼 스타일, 텍스트 표시 스타일 및 기본 응용 프로그램 스레드 (Windows 인증을 사용 하는 응용 프로그램) 하는 경우에 대 한 현재 보안 주체를 설정 및 호출 `ShowSplashScreen` 모두 `/nosplash` 나 `-nosplash` 로 사용 되는 명령줄 인수입니다.  
  
     이 함수에서 반환 하는 경우 응용 프로그램 시작 시퀀스 취소 되 `False`합니다. 이 경우에는 응용 프로그램 실행 되지 하는 경우에 유용할 수 있습니다.  
  
     <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> 메서드 다음 메서드를 호출 합니다.  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>. 응용 프로그램 정의 시작 화면 인지 여부를 결정 하 고 그렇지 않으면 시작 화면을 별도 스레드에 표시 합니다.  
  
         <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> 시작을 표시 하는 코드를 포함 하는 메서드 이상으로 지정 된 밀리초 수에 대 한 화면는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> 속성입니다. 이 기능을 사용 하려면 시작 화면을 더해야를 사용 하 여 응용 프로그램에서 **프로젝트 디자이너** (로 설정 하는 `My.Application.MinimumSplashScreenDisplayTime` 속성을 2 초), 설정 또는 `My.Application.MinimumSplashScreenDisplayTime` 는 를재정의하는메서드에에서속성<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> 또는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> 메서드. 자세한 내용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>을 참조하십시오.  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. 디자이너를를 시작 화면을 초기화 하는 코드를 내보낼 수 있습니다.  
  
         기본적으로이 메서드는 아무 작업도 수행 하지 않습니다. 시작 화면에서 응용 프로그램에 대 한 선택 하는 경우는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] **프로젝트 디자이너**, 디자이너 재정의 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> 메서드를 설정 하는 메서드로 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> 시작 화면의 새 인스턴스를 속성 폼입니다.  
  
2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>. 발생 시키기 위한 확장 지점을 제공는 `Startup` 이벤트입니다. 이 함수를 반환 하는 경우 응용 프로그램 시작 시퀀스 중지 `False`합니다.  
  
     기본적으로이 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> 이벤트입니다. 이벤트 처리기를 설정 하는 경우는 <xref:System.ComponentModel.CancelEventArgs.Cancel> 이벤트 인수의 속성 `True`, 메서드가 반환 `False` 응용 프로그램 시작을 취소 하 합니다.  
  
3.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>. 기본 응용 프로그램 초기화를 완료 한 후 실행을 시작할 준비가 되었을 때에 대 한 시작 지점을 제공 합니다.  
  
     기본적으로 Windows Forms 메시지 루프를 시작 하기 전에이 메서드를 호출는 `OnCreateMainForm` (응용 프로그램의 기본 폼 만들려는) 및 `HideSplashScreen` (시작 화면 닫기)을 메서드:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>. 기본 폼을 초기화 하는 코드를 내보낼 디자이너에 대 한 방법을 제공 합니다.  
  
         기본적으로이 메서드는 아무 작업도 수행 하지 않습니다. 그러나 선택 하면 기본 폼에서 응용 프로그램에 대 한는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] **프로젝트 디자이너**, 디자이너 재정의 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> 메서드를 설정 하는 메서드로 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> 기본 폼의 새 인스턴스를 속성 .  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>. 응용 프로그램에 정의 된 시작 화면이 열려 있는 경우이 메서드는 시작 화면을 닫습니다.  
  
         기본적으로이 메서드는 시작 화면을 닫습니다.  
  
4.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>. 응용 프로그램의 다른 인스턴스가 시작 될 때 단일 인스턴스 응용 프로그램의 작동 방법을 사용자가 지정 하는 방법을 제공 합니다.  
  
     기본적으로이 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 이벤트입니다.  
  
5.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>. 발생 시키기 위한 확장 지점을 제공는 `Shutdown` 이벤트입니다. 이 메서드는 기본 응용 프로그램에서 처리 되지 않은 예외가 발생 하는 경우 실행 되지 않습니다.  
  
     기본적으로이 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> 이벤트입니다.  
  
6.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>. 위의 메서드 중 하나에서 처리 되지 않은 예외가 발생할 경우 실행 합니다.  
  
     기본적으로이 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 디버거가 연결 되어 있지 않습니다 및 처리 하는 응용 프로그램으로 `UnhandledException` 이벤트입니다.  
  
 응용 프로그램의 다음 인스턴스를 호출 하는 응용 프로그램에는 단일 인스턴스 응용 프로그램은 응용 프로그램이 이미 실행 하는 경우는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> 메서드 원래 인스턴스의 응용 프로그램을 한 다음 종료 됩니다.  
 
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> 생성자 호출은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> 응용 프로그램의 폼에 사용할 텍스트 렌더링 엔진을 결정 하는 속성입니다. 기본적으로는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> 속성에서 반환 `False`, GDI 텍스트 렌더링 엔진을 사용 하는 것을 나타내는, 기본값인에 [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)]합니다. 재정의할 수 있습니다는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> 반환할 속성 `True`, GDI + 텍스트 렌더링 엔진을 사용할 수 없음을 나타냅니다 Visual Basic.NET 2002 및 Visual Basic.NET 2003에서 기본값입니다.  
  
## <a name="configuring-the-application"></a>응용 프로그램 구성  
 일부로 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 응용 프로그램 모델의 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering> 클래스 응용 프로그램을 구성 하는 보호 된 속성을 제공 합니다. 이러한 속성을 구현 하는 클래스의 생성자에서 설정 되어야 합니다.  
  
 기본 Windows Forms 프로젝트에서는 **프로젝트 디자이너** 디자이너 설정으로 속성을 설정 하는 코드를 만듭니다. 속성은 응용 프로그램이; 시작 하는 경우에 사용 됩니다. 응용 프로그램이 시작 된 이후에 설정 해도 아무 효과가 없습니다.  
  
|속성|결정|프로젝트 디자이너의 응용 프로그램 창에서 설정|  
|---|---|---|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|여부 응용 프로그램이 단일 인스턴스 또는 다중 인스턴스 응용 프로그램으로 실행 됩니다.|**단일 인스턴스 응용 프로그램** 확인란|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Windows XP와 일치 하는 비주얼 스타일을 사용 하면 응용 프로그램.|**XP 시각적 스타일 사용** 확인란|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|응용 프로그램이 종료 될 때 응용 프로그램을 자동으로 응용 프로그램의 사용자 설정 변경 내용을 저장 합니다.|**종료 시 My.Settings 저장** 확인란|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|어떻게 하면 응용 프로그램이 시작 폼을 닫을 때 또는 마지막 폼을 닫을 때 같은 종료 합니다.|**종료 모드** 목록|  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 [Visual Basic 응용 프로그램 모델 개요](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 [프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
