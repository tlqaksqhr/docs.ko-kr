---
title: "연습: 혼합 응용 프로그램 지역화 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "혼합 응용 프로그램[WPF 상호 운용성]"
  - "지역화[WPF 상호 운용성]"
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 연습: 혼합 응용 프로그램 지역화
이 연습에서는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 기반 혼합 응용 프로그램에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소를 지역화하는 방법을 보여 줍니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 호스트 프로젝트 만들기  
  
-   지역화할 수 있는 콘텐츠 추가  
  
-   지역화 사용  
  
-   리소스 식별자 할당  
  
-   LocBaml 도구를 사용하여 위성 어셈블리 생성  
  
 이 연습에서 설명하는 작업의 전체 코드 목록은 [Localizing a Hybrid Application 샘플](http://go.microsoft.com/fwlink/?LinkID=160015)을 참조하십시오.  
  
 작업을 마치면 지역화된 혼합 응용 프로그램이 생성됩니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## Windows Forms 호스트 프로젝트 만들기  
 첫 번째 단계는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램 프로젝트를 만들고 지역화할 콘텐츠와 함께 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소를 추가하는 것입니다.  
  
#### 호스트 프로젝트를 만들려면  
  
1.  `LocalizingWpfInWf`라는 WPF 응용 프로그램 프로젝트를 만듭니다.  자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
2.  `SimpleControl`이라는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 요소를 프로젝트에 추가합니다.  
  
3.  <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 사용하여 `SimpleControl` 요소를 폼에 배치합니다.  자세한 내용은 [연습: Windows Forms에서 3\-D WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)을 참조하십시오.  
  
## 지역화할 수 있는 콘텐츠 추가  
 다음으로는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 레이블 컨트롤을 추가하고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소의 콘텐츠를 지역화할 수 있는 문자열로 설정합니다.  
  
#### 지역화할 수 있는 콘텐츠를 추가하려면  
  
1.  솔루션 탐색기에서 **SimpleControl.xaml**을 두 번 클릭하여 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]에서 엽니다.  
  
2.  다음 코드를 사용하여 <xref:System.Windows.Controls.Button> 컨트롤의 콘텐츠를 설정합니다.  
  
     [!code-xml[LocalizingWpfInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]  
  
3.  솔루션 탐색기에서 **Form1**을 두 번 클릭하여 Windows Forms 디자이너에서 엽니다.  
  
4.  도구 상자를 열고 **레이블**을 두 번 클릭하여 레이블 컨트롤을 폼에 추가합니다.  해당 <xref:System.Windows.Forms.Control.Text%2A> 속성의 값을 `"Hello"`로 설정합니다.  
  
5.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
     `SimpleControl` 요소와 레이블 컨트롤이 모두 **"Hello"** 텍스트를 표시합니다.  
  
## 지역화 사용  
 Windows Forms 디자이너는 위성 어셈블리에서 지역화를 사용하기 위한 설정을 제공합니다.  
  
#### 지역화를 사용하려면  
  
1.  솔루션 탐색기에서  **Form1.cs**를 두 번 클릭하여 Windows Forms 디자이너에서 엽니다.  
  
2.  속성 창에서 폼의 **Localizable** 속성 값을 `true`로 설정합니다.  
  
3.  속성 창에서 **Language** 속성의 값을 **Spanish \(Spain\)**로 설정합니다.  
  
4.  Windows Forms 디자이너에서 레이블 컨트롤을 선택합니다.  
  
5.  속성 창에서 <xref:System.Windows.Forms.Control.Text%2A> 속성의 값을 `"Hola"`로 설정합니다.  
  
     Form1.es\-ES.resx라는 새 리소스 파일이 프로젝트에 추가됩니다.  
  
6.  솔루션 탐색기에서  **Form1.cs**를 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭하여 코드 편집기에서 해당 파일을 엽니다.  
  
7.  `InitializeComponent`를 호출하기 전에 다음 코드를 `Form1` 생성자에 복사합니다.  
  
     [!code-csharp[LocalizingWpfInWf#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]  
  
8.  솔루션 탐색기에서 **LocalizingWpfInWf**를 마우스 오른쪽 단추로 클릭하고 **프로젝트 언로드**를 클릭합니다.  
  
     프로젝트 이름이 **\(unavailable\)**이라고 지정됩니다.  
  
9. **LocalizingWpfInWf**를 마우스 오른쪽 단추로 클릭하고 **LocalizingWpfInWf.csproj 편집**을 클릭합니다.  
  
     프로젝트 파일이 코드 편집기에서 열립니다.  
  
10. 다음 줄이 프로젝트 파일의 첫 번째 `PropertyGroup`에 복사됩니다.  
  
    ```  
    <UICulture>en-US</UICulture>   
    ```  
  
11. 프로젝트 파일을 저장하고 닫습니다.  
  
12. 솔루션 탐색기에서 **LocalizingWpfInWf**를 마우스 오른쪽 단추로 클릭하고 **프로젝트 다시 로드**를 클릭합니다.  
  
## 리소스 식별자 할당  
 리소스 식별자를 사용하여 지역화 가능한 콘텐츠를 리소스 어셈블리에 매핑할 수 있습니다.  `updateuid` 옵션을 지정하면 MsBuild.exe 응용 프로그램에서 리소스 식별자를 자동으로 할당합니다.  
  
#### 리소스 식별자를 할당하려면  
  
1.  시작 메뉴에서 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 명령 프롬프트를 엽니다.  
  
2.  다음 명령을 사용하여 리소스 식별자를 지역화 가능한 콘텐츠에 할당합니다.  
  
    ```  
    msbuild /t:updateuid LocalizingWpfInWf.csproj  
    ```  
  
3.  솔루션 탐색기에서 **SimpleControl.xaml**을 두 번 클릭하여 코드 편집기에서 엽니다.  `msbuild` 명령에서 `Uid` 특성을 모든 요소에 추가했음을 알 수 있습니다.  따라서 리소스 식별자 할당을 통해 지역화가 용이해집니다.  
  
     [!code-xml[LocalizingWpfInWf#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]  
  
4.  F6 키를 눌러 솔루션을 빌드합니다.  
  
## LocBaml을 사용하여 위성 어셈블리 생성  
 지역화된 콘텐츠는 리소스 전용 *위성 어셈블리*에 저장됩니다.  명령줄 도구 LocBaml.exe를 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠에 대해 지역화된 어셈블리를 생성할 수 있습니다.  
  
#### 위성 어셈블리를 생성하려면  
  
1.  LocBaml.exe를 프로젝트의 obj\\Debug 폴더에 복사합니다.  자세한 내용은 [응용 프로그램 지역화](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)를 참조하십시오.  
  
2.  명령 프롬프트 창에서 다음 명령을 사용하여 리소스 문자열을 임시 파일로 추출합니다.  
  
    ```  
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv  
    ```  
  
3.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 또는 다른 텍스트 편집기를 사용하여 temp.csv 파일을 엽니다.  문자열 `"Hello"`를 스페인어 번역인 `"Hola"`로 바꿉니다.  
  
4.  temp.csv 파일을 저장합니다.  
  
5.  다음 명령을 사용하여 지역화된 리소스 파일을 생성합니다.  
  
    ```  
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES  
    ```  
  
     LocalizingWpfInWf.g.es\-ES.resources 파일이 obj\\Debug 폴더에 생성됩니다.  
  
6.  다음 명령을 사용하여 지역화된 위성 어셈블리를 빌드합니다.  
  
    ```  
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources  
    ```  
  
     LocalizingWpfInWf.resources.dll 파일이 obj\\Debug 폴더에 생성됩니다.  
  
7.  LocalizingWpfInWf.resources.dll 파일을 프로젝트의 bin\\Debug\\es\-ES 폴더에 복사합니다.  기존 파일을 바꿉니다.  
  
8.  프로젝트의 bin\\Debug 폴더에 있는 LocalizingWpfInWf.exe를 실행합니다.  응용 프로그램을 다시 빌드하지 마십시오. 다시 빌드하면 위성 어셈블리를 덮어씁니다.  
  
     응용 프로그램은 영어 문자열 대신 지역화된 문자열을 표시합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [응용 프로그램 지역화](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)   
 [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5)   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)