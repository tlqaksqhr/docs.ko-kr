---
title: "방법: 간단한 Windows Forms 컨트롤 개발 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Control 클래스, Windows Forms"
  - "컨트롤[Windows Forms]"
  - "사용자 지정 컨트롤[Windows Forms], 코드를 사용하여 간단한 컨트롤 만들기"
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: 간단한 Windows Forms 컨트롤 개발
이 단원에서는 사용자 지정 Windows Forms 컨트롤을 만드는 주요 단계를 설명합니다.  이 연습에서 개발한 간단한 컨트롤을 사용하면 해당 <xref:System.Windows.Forms.Control.Text%2A> 속성의 맞춤을 변경할 수 있습니다.  이 컨트롤은 이벤트를 발생시키거나 처리하지 않습니다.  
  
### 사용자 지정 단순 컨트롤을 만들려면  
  
1.  <xref:System.Windows.Forms.Control?displayProperty=fullName>에서 파생되는 클래스를 정의합니다.  
  
    ```vb  
    Public Class FirstControl  
       Inherits Control  
  
    End Class  
    ```  
  
    ```csharp  
    public class FirstControl:Control{}  
    ```  
  
2.  속성을 정의합니다.  컨트롤의 많은 속성은 <xref:System.Windows.Forms.Control> 클래스에서 상속되기 때문에 속성을 정의하지 않아도 되지만 대부분의 사용자 지정 컨트롤에서는 일반적으로 추가 속성을 정의합니다. 명명 된 속성을 정의 하는 다음 코드와 `TextAlignment` 는`FirstControl` 의 표시 형식을 지정 하는 <xref:System.Windows.Forms.Control.Text%2A> 속성에서 상속 된 <xref:System.Windows.Forms.Control>.  속성 정의에 대한 자세한 내용은 [속성 개요](../Topic/Properties%20Overview.md)를 참조하십시오.  
  
     [!code-csharp[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]  
  
     컨트롤의 시각적 표시를 변경하는 속성을 설정하는 경우 <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드를 호출하여 컨트롤을 다시 그려야 합니다.  <xref:System.Windows.Forms.Control.Invalidate%2A>는 기본 클래스 <xref:System.Windows.Forms.Control>에 정의되어 있습니다.  
  
3.  <xref:System.Windows.Forms.Control>에서 상속된 보호된 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의하여 컨트롤에 렌더링 논리를 제공합니다.  <xref:System.Windows.Forms.Control.OnPaint%2A>를 재정의하지 않으면 컨트롤은 자신을 그릴 수 없습니다.  다음 코드 조각에서 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 <xref:System.Windows.Forms.Control>에서 상속된 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `alignmentValue` 필드에서 지정한 맞춤으로 표시합니다.  
  
     [!code-csharp[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]  
  
4.  컨트롤에 대한 특성을 제공합니다.  특성을 사용하면 비주얼 디자이너는 컨트롤과 해당 속성 및 이벤트를 디자인 타임에 적절하게 표시할 수 있습니다.  다음 코드 조각에서는 `TextAlignment` 속성에 특성을 적용합니다.  Visual Studio와 같은 디자이너에서 코드 조각에 나타난 것과 같은 <xref:System.ComponentModel.CategoryAttribute.Category%2A> 특성을 사용하면 속성이 논리 범주 아래에 표시됩니다.  <xref:System.ComponentModel.DescriptionAttribute.Description%2A> 특성을 사용하면 `TextAlignment` 속성을 선택한 경우 **속성** 창 아래쪽에 설명 문자열이 표시됩니다.  특성에 대한 자세한 내용은 [구성 요소의 디자인 타임 특성](../Topic/Design-Time%20Attributes%20for%20Components.md)을 참조하십시오.  
  
     [!code-csharp[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]  
  
5.  \(선택적 요소\) 컨트롤에 리소스를 제공합니다.  컨트롤과 함께 리소스를 패키지하는 컴파일러 옵션\(C\#의 경우 `/res`\)을 사용하여 컨트롤에 비트맵과 같은 리소스를 제공할 수 있습니다.  런타임에 <xref:System.Resources.ResourceManager> 클래스의 메서드를 사용하여 이러한 리소스를 검색할 수 있습니다.  리소스 만들기 및 사용에 대한 자세한 내용은 [데스크톱 응용 프로그램의 리소스](../../../../docs/framework/resources/index.md)를 참조하십시오.  
  
6.  컨트롤을 컴파일하고 배포합니다.  `FirstControl,`을 컴파일하고 배포하려면 다음 단계를 실행합니다.  
  
    1.  다음 샘플의 코드를 소스 파일\(예:FirstControl.cs 또는 FirstControl.vb\)로 저장합니다.  
  
    2.  소스 코드를 어셈블리로 컴파일하고 응용 프로그램의 디렉터리에 저장합니다.  이를 수행하려면 소스 파일을 포함하는 디렉터리에서 다음 명령을 실행합니다.  
  
        ```vb  
        vbc /t:library /out:[path to your application's directory]/CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll FirstControl.vb  
        ```  
  
        ```csharp  
        csc /t:library /out:[path to your application's directory]/CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll FirstControl.cs  
        ```  
  
         `/t:library` 컴파일러 옵션은 사용자가 작성하는 어셈블리가 실행 파일이 아니라 라이브러리임을 컴파일러에 알려 줍니다.  `/out` 옵션은 어셈블리의 경로와 이름을 지정합니다.  `/r` 옵션은 코드에서 참조하는 어셈블리의 이름을 제공합니다.  이 예제에서는 사용자 응용 프로그램에서만 사용할 수 있는 전용 어셈블리를 만듭니다.  따라서 이것은 사용자 응용 프로그램의 디렉터리에 저장되어야 합니다.  배포를 위한 컨트롤 패키지 및 배포에 대한 자세한 내용은 [배포](../../../../docs/framework/deployment/net-framework-and-applications.md)를 참조하십시오.  
  
 다음 샘플에서는 `FirstControl`에 대한 코드를 보여 줍니다.  컨트롤은 `CustomWinControls` 네임스페이스에 포함되어 있습니다.  네임스페이스는 관련된 형식의 논리적 그룹화를 제공합니다.  새로운 네임스페이스나 기존의 네임스페이스에서 컨트롤을 만들 수 있습니다.  C\#에서 `using` 선언\(Visual Basic의 경우 `Imports`\)을 사용하면 네임스페이스에서 형식의 정규화된 이름을 사용하지 않고도 형식에 액세스할 수 있습니다.  다음 예제에서는 `using` 선언을 통해 코드가 정규화된 이름 <xref:System.Windows.Forms.Control?displayProperty=fullName>을 사용하는 대신 <xref:System.Windows.Forms?displayProperty=fullName>에서 <xref:System.Windows.Forms.Control>로 간단히 <xref:System.Windows.Forms.Control> 클래스에 액세스합니다.  
  
 [!code-csharp[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
 [!code-vb[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]  
  
## 폼에서 사용자 지정 컨트롤 사용  
 다음 예제에서는 `FirstControl`을 사용하는 간단한 폼을 보여 줍니다.  여기서는 `TextAlignment` 속성에 대해 각각 다른 값을 갖고 있는 `FirstControl`의 세 가지 인스턴스를 만듭니다.  
  
#### 이 샘플을 컴파일하고 실행하려면  
  
1.  다음 예제의 코드를 소스 파일\(SimpleForm.cs 또는 SimpleForms.vb\)로 저장합니다.  
  
2.  소스 파일을 포함하는 디렉터리에서 다음 명령을 실행하여 소스 코드를 실행 가능한 어셈블리로 컴파일합니다.  
  
    ```vb  
    vbc /r:CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll SimpleForm.vb  
    ```  
  
    ```csharp  
    csc /r:CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll SimpleForm.cs  
    ```  
  
     CustomWinControls.dll은 `FirstControl` 클래스를 포함하는 어셈블리입니다.  이 어셈블리는 여기에 액세스하는 폼의 소스 파일\(SimpleForm.cs 또는 SimpleForms.vb\)과 같은 디렉터리에 있어야 합니다.  
  
3.  다음 명령을 사용하여 SimpleForm.exe를 실행합니다.  
  
    ```  
    SimpleForm  
    ```  
  
 [!code-csharp[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
 [!code-vb[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]  
  
## 참고 항목  
 [Windows Forms 컨트롤의 속성](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [Windows Forms 컨트롤의 이벤트](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)