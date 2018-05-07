---
title: '연습: 혼합 응용 프로그램 지역화'
ms.date: 03/30/2017
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 010c8f75a1151f5606be5ffa63d60fca364bdb59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>연습: 혼합 응용 프로그램 지역화
이 연습에서는 지역화 하는 방법을 보여 줍니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 의 요소는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-하이브리드 응용 프로그램을 기반으로 합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   만들기는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 호스트 프로젝트.  
  
-   지역화 가능한 콘텐츠 추가.  
  
-   지역화 사용.  
  
-   리소스 식별자 할당.  
  
-   LocBaml 도구를 사용하여 위성 어셈블리 생성.  
  
 이 연습에서 설명 하는 작업의 전체 코드 목록을 보려면 [하이브리드 응용 프로그램 샘플 지역화](http://go.microsoft.com/fwlink/?LinkID=160015)합니다.  
  
 위의 작업을 완료하면 지역화된 하이브리드 응용 프로그램이 구현됩니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-windows-forms-host-project"></a>Windows Forms 호스트 프로젝트 만들기  
 첫 번째 단계를 만드는 것은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램 프로젝트 및 추가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 지역화 됩니다 하는 콘텐츠가 있는 요소의 합니다.  
  
#### <a name="to-create-the-host-project"></a>호스트 프로젝트 만들기  
  
1.  이라는 WPF 응용 프로그램 프로젝트 만들기 `LocalizingWpfInWf`합니다. 자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.  
  
2.  추가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 라는 이름의 요소 `SimpleControl` 프로젝트에 있습니다.  
  
3.  사용 하 여는 <xref:System.Windows.Forms.Integration.ElementHost> 배치할은 `SimpleControl` 요소를 폼에 있습니다. 자세한 내용은 참조 [연습: Windows Forms에서 WPF 3 차원 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)합니다.  
  
## <a name="adding-localizable-content"></a>지역화 가능한 콘텐츠 추가  
 추가한 다음으로 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 레이블 지정 및 설정는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 지역화 가능한 문자열 요소의 콘텐츠입니다.  
  
#### <a name="to-add-localizable-content"></a>지역화 가능한 콘텐츠를 추가하려면  
  
1.  솔루션 탐색기에서 두 번 클릭 **SimpleControl.xaml** 에서 열려는 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]합니다.  
  
2.  설정의 콘텐츠는 <xref:System.Windows.Controls.Button> 다음 코드를 사용 하 여 제어 합니다.  
  
     [!code-xaml[LocalizingWpfInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]  
  
3.  솔루션 탐색기에서 두 번 클릭 **Form1** Windows Forms 디자이너에서 엽니다.  
  
4.  도구 상자를 열고 두 번 클릭 **레이블** 를 양식에 레이블 컨트롤을 추가 합니다. <xref:System.Windows.Forms.Control.Text%2A> 속성의 값을 `"Hello"`로 설정합니다.  
  
5.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
     두는 `SimpleControl` 요소와 레이블 컨트롤에 텍스트 표시 **"Hello"** 합니다.  
  
## <a name="enabling-localization"></a>지역화 사용  
 Windows Forms 디자이너에서는 위성 어셈블리에서 지역화를 사용하도록 설정하기 위한 설정을 제공합니다.  
  
#### <a name="to-enable-localization"></a>지역화를 사용하려면  
  
1.  솔루션 탐색기에서 두 번 클릭 **Form1.cs** Windows Forms 디자이너에서 엽니다.  
  
2.  속성 창에서 폼의 값을 설정 **Localizable** 속성을 `true`합니다.  
  
3.  속성 창에서 설정의 값은 **언어** 속성을 **스페인어 (스페인)** 합니다.  
  
4.  Windows Forms 디자이너에서 레이블 컨트롤을 선택합니다.  
  
5.  속성 창에서 설정의 값은 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `"Hola"`합니다.  
  
     Form1.es-ES.resx라는 새 리소스 파일이 프로젝트에 추가됩니다.  
  
6.  솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 **Form1.cs** 클릭 **코드 보기** 코드 편집기에서 엽니다.  
  
7.  다음 코드를 복사는 `Form1` 생성자를 호출 하기 `InitializeComponent`합니다.  
  
     [!code-csharp[LocalizingWpfInWf#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]  
  
8.  솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 **LocalizingWpfInWf** 클릭 **프로젝트 언로드**합니다.  
  
     프로젝트 이름 레이블이 **(사용 불가)** 합니다.  
  
9. 마우스 오른쪽 단추로 클릭 **LocalizingWpfInWf**를 클릭 하 고 **편집 LocalizingWpfInWf.csproj**합니다.  
  
     프로젝트 파일이 코드 편집기에서 열립니다.  
  
10. 다음 줄을 첫 번째 복사 `PropertyGroup` 프로젝트 파일에 있습니다.  
  
    ```xml  
    <UICulture>en-US</UICulture>   
    ```  
  
11. 프로젝트 파일을 저장하고 닫습니다.  
  
12. 솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 **LocalizingWpfInWf** 클릭 **프로젝트 다시 로드**합니다.  
  
## <a name="assigning-resource-identifiers"></a>리소스 식별자 할당  
 리소스 식별자를 사용하여 리소스 어셈블리에 지역화 가능한 콘텐츠를 매핑할 수 있습니다. 지정 하는 경우 MsBuild.exe 응용 프로그램 리소스 식별자를 자동으로 할당 된 `updateuid` 옵션입니다.  
  
#### <a name="to-assign-resource-identifiers"></a>리소스 식별자를 할당하려면  
  
1.  시작 메뉴에서 Visual Studio 명령 프롬프트를 엽니다.  
  
2.  다음 명령을 사용하여 지역화 가능한 콘텐츠에 리소스 식별자를 할당합니다.  
  
    ```  
    msbuild /t:updateuid LocalizingWpfInWf.csproj  
    ```  
  
3.  솔루션 탐색기에서 두 번 클릭 **SimpleControl.xaml** 코드 편집기에서 엽니다. 가 표시 됩니다는 `msbuild` 명령에 추가 `Uid` 모든 요소에 특성입니다. 따라서 리소스 식별자 할당을 통해 지역화가 용이해집니다.  
  
     [!code-xaml[LocalizingWpfInWf#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]  
  
4.  F6 키를 눌러 솔루션을 빌드합니다.  
  
## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>LocBaml을 사용하여 위성 어셈블리 생성  
 리소스 전용에 지역화 된 콘텐츠 저장 됩니다 *위성 어셈블리*합니다. 에 대 한 지역화 된 어셈블리를 생성 하기 LocBaml.exe 명령줄 도구를 사용 하 여 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠입니다.  
  
#### <a name="to-produce-a-satellite-assembly"></a>위성 어셈블리를 생성하려면  
  
1.  LocBaml.exe를 프로젝트의 obj\Debug 폴더에 복사합니다. 자세한 내용은 참조 [응용 프로그램 지역화](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)합니다.  
  
2.  [명령 프롬프트] 창에서 다음 명령을 사용하여 리소스 문자열을 임시 파일로 추출합니다.  
  
    ```  
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv  
    ```  
  
3.  Visual Studio 또는 다른 텍스트 편집기와 함께 사용 하 여 temp.csv 파일을 엽니다. 문자열 `"Hello"` 해당 스페인어 번역 된 `"Hola"`합니다.  
  
4.  temp.csv 파일을 저장합니다.  
  
5.  다음 명령을 사용하여 지역화된 리소스 파일을 생성합니다.  
  
    ```  
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES  
    ```  
  
     LocalizingWpfInWf.g.es-ES.resources 파일이 obj\Debug 폴더에 만들어집니다.  
  
6.  다음 명령을 사용하여 지역화된 위성 어셈블리를 빌드합니다.  
  
    ```  
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources  
    ```  
  
     LocalizingWpfInWf.resources.dll 파일이 obj\Debug 폴더에 만들어집니다.  
  
7.  LocalizingWpfInWf.resources.dll 파일을 프로젝트의 bin\Debug\es-ES 폴더에 복사합니다. 기존 파일을 바꿉니다.  
  
8.  프로젝트의 bin\Debug 폴더에 있는 LocalizingWpfInWf.exe를 실행합니다. 응용 프로그램을 다시 빌드하지 마세요. 다시 빌드하면 위성 어셈블리가 덮어 쓰입니다.  
  
     응용 프로그램에서 영어 문자열 대신 지역화된 문자열을 표시합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [응용 프로그램 지역화](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)  
 [연습: Windows Forms 지역화](http://msdn.microsoft.com/library/9a96220d-a19b-4de0-9f48-01e5d82679e5)  
 [WPF 디자이너](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
