---
title: "연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], snaplines를 사용하여 정렬"
  - "SnapLine 클래스, 연습"
  - "맞춤선, Windows Forms 컨트롤 정렬"
  - "Windows Forms 컨트롤, 정렬"
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# 연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬
많은 응용 프로그램에 있어 폼에 컨트롤을 정확하게 배치하는 작업은 매우 중요합니다.  Windows Forms 디자이너에서는 이러한 작업을 위한 여러 가지 레이아웃 도구를 제공합니다.  가장 중요한 기능 중 하나가 <xref:System.Windows.Forms.Design.Behavior.SnapLine>입니다.  
  
 맞춤선은 컨트롤을 다른 컨트롤과 맞출 정확한 위치를 보여 줍니다.  또한 Windows 사용자 인터페이스 지침에 지정된 컨트롤 간 여백에 대한 권장 간격을 보여 줍니다.  자세한 내용은 [User Interface Design and Development\(사용자 인터페이스 디자인 및 개발\)](http://go.microsoft.com/FWLink/?LinkId=83878)를 참조하십시오.  
  
 맞춤선을 사용하면 컨트롤이 보다 전문적인 모양과 동작\(모양 및 느낌\)을 가질 수 있도록 컨트롤을 쉽게 정렬할 수 있습니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   Windows Forms 프로젝트 만들기  
  
-   맞춤선을 사용하여 컨트롤 간격 조정 및 맞춤  
  
-   폼 및 컨테이너 여백에 맞춤  
  
-   그룹화된 컨트롤에 맞춤  
  
-   컨트롤 크기를 윤곽선으로 지정하여 컨트롤을 배치하는 데 맞춤선 사용  
  
-   도구 상자에서 컨트롤을 끄는 데 맞춤선 사용  
  
-   맞춤선을 사용하여 컨트롤 크기 조정  
  
-   컨트롤의 텍스트에 레이블 맞춤  
  
-   키보드 탐색에 맞춤선 사용  
  
-   맞춤선 및 레이아웃 패널  
  
-   맞춤선 해제  
  
 작업이 끝나면 맞춤선 기능이 수행하는 레이아웃 역할을 이해할 수 있게 됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### 프로젝트를 만들려면  
  
1.  "SnaplineExample"이라고 하는 Windows 기반 응용 프로그램 프로젝트를 만듭니다.  자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
2.  폼 디자이너에서 폼을 선택합니다.  
  
## 맞춤선을 사용하여 컨트롤 간격 조정 및 맞춤  
 맞춤선은 정확하고 간단하게 폼에 컨트롤을 맞추는 방법을 제공합니다.  선택한 컨트롤을 다른 컨트롤이나 컨트롤 집합에 맞출 위치 주위로 이동하면 맞춤선이 나타납니다.  선택한 컨트롤을 다른 컨트롤로 이동하면 선택한 컨트롤이 제안된 위치에 "맞춰집니다".  
  
#### 맞춤선을 사용하여 컨트롤을 정렬하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  <xref:System.Windows.Forms.Button> 컨트롤을 폼의 오른쪽 아래 모퉁이로 이동합니다.  <xref:System.Windows.Forms.Button> 컨트롤이 폼의 아래쪽 모퉁이와 오른쪽 모퉁이에 접근하면 맞춤선이 나타납니다.  이러한 맞춤선은 컨트롤과 폼의 테두리 간 권장 간격을 표시합니다.  
  
3.  <xref:System.Windows.Forms.Button> 컨트롤을 폼의 테두리 주위로 이동하고 맞춤선이 나타나는 위치를 확인합니다.  작업이 끝나면 <xref:System.Windows.Forms.Button> 컨트롤을 폼의 가운데 주위로 이동합니다.  
  
4.  **도구 상자**의 다른 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌어 옵니다.  
  
5.  두 번째 <xref:System.Windows.Forms.Button> 컨트롤이 첫 번째 컨트롤이 있는 수준과 가까워질 때까지 두 번째 컨트롤을 이동합니다.  맞춤선이 두 단추의 텍스트 기준선에 나타나고 이동하는 컨트롤이 다른 컨트롤이 있는 수준의 위치에 맞춰집니다.  
  
6.  두 번째 <xref:System.Windows.Forms.Button> 컨트롤이 첫 번째 컨트롤 바로 위에 배치될 때까지 두 번째 컨트롤을 이동합니다.  맞춤선이 두 단추의 왼쪽 가장자리와 오른쪽 가장자리에 나타나고 이동하는 컨트롤이 다른 컨트롤에 정렬되는 위치에 맞춰집니다.  
  
7.  <xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택하고 다른 컨트롤에 거의 닿을 때까지 가깝게 이동합니다.  이러한 컨트롤 사이에 맞춤선이 나타납니다.  컨트롤 테두리 사이에 이 간격을 사용하는 것이 좋습니다.  또한 이동 중인 컨트롤이 이 위치에 맞춰집니다.  
  
8.  **도구 상자**의 두 개의 <xref:System.Windows.Forms.Panel> 컨트롤을 폼으로 끌어 옵니다.  
  
9. <xref:System.Windows.Forms.Panel> 컨트롤 중 하나가 첫 번째 컨트롤이 있는 수준과 가까워질 때까지 해당 컨트롤을 이동합니다.  맞춤선이 두 컨트롤의 위쪽 가장자리와 아래쪽 가장자리에 나타나고 이동하는 컨트롤이 다른 컨트롤이 있는 수준의 위치에 맞춰집니다.  
  
## 폼 및 컨테이너 여백에 맞춤  
 맞춤선은 컨트롤을 폼 및 컨테이너 여백에 일관된 방식으로 맞추는 데 도움을 줍니다.  
  
#### 폼 및 컨테이너 여백에 컨트롤을 맞추려면  
  
1.  <xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택하여 맞춤선이 나타날 때까지 폼의 오른쪽 테두리에 가깝게 이동합니다.  오른쪽 테두리에서의 맞춤선 간격은 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성과 폼의 <xref:System.Windows.Forms.Control.Padding%2A> 속성 값을 합한 것입니다.  
  
> [!NOTE]
>  폼의 <xref:System.Windows.Forms.Control.Padding%2A> 속성이 0,0,0,0으로 설정된 경우 Windows Forms Designer에서 숨겨진 <xref:System.Windows.Forms.Control.Padding%2A> 값 9,9,9,9를 폼에 지정합니다.  이 동작을 재정의하려면 0,0,0,0 이외의 값을 할당합니다.  
  
1.  **속성** 창에서 <xref:System.Windows.Forms.Control.Margin%2A> 항목을 확장하고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 10으로 설정하여 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성 값을 변경합니다.  자세한 내용은 [연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)을 참조하십시오.  
  
2.  맞춤선이 나타날 때까지 <xref:System.Windows.Forms.Button> 컨트롤을 폼의 오른쪽 테두리에 가깝게 이동합니다.  이 간격은 폼의 <xref:System.Windows.Forms.Control.Padding%2A> 속성 값에서 제공됩니다.  
  
3.  **도구 상자**의 <xref:System.Windows.Forms.GroupBox> 컨트롤을 폼으로 끌어 옵니다.  
  
4.  **속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 항목을 확장하고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 10으로 설정하여 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성 값을 변경합니다.  
  
5.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.GroupBox> 컨트롤로 끌어 옵니다.  
  
6.  맞춤선이 나타날 때까지 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.GroupBox> 컨트롤의 오른쪽 테두리에 가깝게 이동합니다.  <xref:System.Windows.Forms.GroupBox> 컨트롤 내에서 <xref:System.Windows.Forms.Button> 컨트롤을 이동하고 맞춤선이 나타나는 위치를 확인합니다.  
  
## 그룹화된 컨트롤에 맞춤  
 맞춤선을 사용하여 <xref:System.Windows.Forms.GroupBox> 컨트롤 내에서 컨트롤뿐만 아니라 그룹화된 컨트롤을 맞출 수 있습니다.  
  
#### 그룹화된 컨트롤에 맞추려면  
  
1.  폼에서 두 개의 컨트롤을 선택합니다.  선택한 컨트롤을 이동하면 선택한 컨트롤과 다른 컨트롤 사이에 맞춤선이 나타납니다.  
  
2.  **도구 상자**의 <xref:System.Windows.Forms.GroupBox> 컨트롤을 폼으로 끌어 옵니다.  
  
3.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.GroupBox> 컨트롤로 끌어 옵니다.  
  
4.  <xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택하여 <xref:System.Windows.Forms.GroupBox> 컨트롤 주위로 이동합니다.  맞춤선이 <xref:System.Windows.Forms.GroupBox> 컨트롤의 가장자리에 나타납니다.  또한 맞춤선이 <xref:System.Windows.Forms.GroupBox> 컨트롤에 포함된 <xref:System.Windows.Forms.Button> 컨트롤의 가장자리에 나타납니다.  컨테이너 컨트롤의 자식 컨트롤도 맞춤선을 지원합니다.  
  
## 컨트롤 크기를 윤곽선으로 지정하여 컨트롤을 배치하는 데 맞춤선 사용  
 맞춤선은 폼에 컨트롤을 처음 배치하는 경우 컨트롤을 맞추는 데 도움을 줍니다.  
  
#### 컨트롤 크기를 윤곽선으로 지정하여 컨트롤을 배치하는 데 맞춤선을 사용하려면  
  
1.  **도구 상자**에서 <xref:System.Windows.Forms.Button> 컨트롤 아이콘을 클릭합니다.  이 때 컨트롤을 폼으로 끌어 오지 마십시오.  
  
2.  마우스 포인터를 폼의 디자인 화면으로 이동합니다.  포인터가 <xref:System.Windows.Forms.Button> 컨트롤 아이콘이 연결된 십자형으로 변경됩니다.  또한 <xref:System.Windows.Forms.Button> 컨트롤의 맞춤 위치를 제안하는 맞춤선이 나타납니다.  
  
3.  마우스 단추를 클릭한 채로 있습니다.  
  
4.  마우스 포인터를 폼 주위로 끕니다.  컨트롤의 위치와 크기를 나타내는 윤곽선이 그려집니다.  
  
5.  컨트롤이 폼의 다른 컨트롤에 맞춰질 때까지 포인터를 끕니다.  맞춤을 나타내는 맞춤선이 나타납니다.  
  
6.  마우스 단추를 놓습니다.  윤곽선으로 표시된 위치와 크기로 컨트롤이 만들어집니다.  
  
## 도구 상자에서 컨트롤을 끄는 데 맞춤선 사용  
 맞춤선은 **도구 상자**의 컨트롤을 폼으로 끌 때 컨트롤을 맞추는 데 도움이 됩니다.  
  
#### 도구 상자에서 컨트롤을 끄는 데 맞춤선을 사용하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌고 마우스 단추를 클릭한 채로 있습니다.  
  
2.  마우스 포인터를 폼의 디자인 화면으로 이동합니다.  포인터가 변경되어 새 <xref:System.Windows.Forms.Button> 컨트롤이 만들어지는 위치를 나타냅니다.  
  
3.  마우스 포인터를 폼 주위로 끕니다.  <xref:System.Windows.Forms.Button> 컨트롤의 맞춤 위치를 제안하는 맞춤선이 나타납니다.  다른 컨트롤에 정렬되는 위치를 찾습니다.  
  
4.  마우스 단추를 놓습니다.  맞춤선이 나타낸 위치에 컨트롤이 만들어집니다.  
  
## 맞춤선을 사용하여 컨트롤 크기 조정  
 맞춤선은 컨트롤 크기를 조정할 때 컨트롤을 맞추는 데 도움을 줍니다.  
  
#### 맞춤선을 사용하여 컨트롤 크기를 조정하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  모퉁이 크기 조정 핸들 중 하나를 선택하고 끌어서 <xref:System.Windows.Forms.Button> 컨트롤의 크기를 조정합니다.  자세한 내용은 [방법: Windows Forms에서 컨트롤의 크기 조정](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)을 참조하십시오.  
  
3.  <xref:System.Windows.Forms.Button> 컨트롤의 테두리 중 하나가 다른 컨트롤에 맞춰질 때까지 크기 조정 핸들을 끕니다.  맞춤선이 나타납니다.  또한 크기 조정 핸들이 맞춤선이 나타낸 위치에 맞춰집니다.  
  
4.  다른 방향에서 <xref:System.Windows.Forms.Button> 컨트롤의 크기를 조정하고 크기 조정 핸들을 다른 컨트롤에 맞춥니다.  맞춤을 나타내는 맞춤선이 여러 방향에서 표시되는 방식을 확인합니다.  
  
## 컨트롤의 텍스트에 레이블 맞춤  
 일부 컨트롤은 표시된 텍스트에 다른 컨트롤을 맞추기 위해 맞춤선을 제공합니다.  
  
#### 컨트롤의 텍스트에 레이블을 맞추려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.TextBox> 컨트롤을 폼으로 끌어 옵니다.  <xref:System.Windows.Forms.TextBox> 컨트롤을 폼으로 끌어 올 때 스마트 태그 문자 모양을 클릭하고 **TextBox1에 텍스트 맞추기** 옵션을 선택합니다.  자세한 내용은 [연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)을 참조하십시오.  
  
2.  **도구 상자**의 <xref:System.Windows.Forms.Label> 컨트롤을 폼으로 끌어 옵니다.  
  
3.  <xref:System.Windows.Forms.Label> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다.  컨트롤의 테두리가 표시된 텍스트에 맞게 조정됩니다.  
  
4.  <xref:System.Windows.Forms.Label> 컨트롤을 <xref:System.Windows.Forms.TextBox> 컨트롤의 왼쪽으로 이동하여 <xref:System.Windows.Forms.TextBox> 컨트롤의 아래쪽 가장자리에 맞춥니다.  맞춤선이 두 컨트롤의 아래쪽 가장자리에 나타납니다.  
  
5.  <xref:System.Windows.Forms.Label> 텍스트 및 <xref:System.Windows.Forms.TextBox> 텍스트가 맞춰질 때까지 <xref:System.Windows.Forms.Label>컨트롤을 조금 위쪽으로 이동합니다.  두 컨트롤의 텍스트 필드가 맞춰졌음을 나타내는 다른 스타일의 맞춤선이 나타납니다.  
  
## 키보드 탐색에 맞춤선 사용  
 맞춤선은 키보드의 화살표 키를 사용하여 컨트롤을 정렬할 때 컨트롤을 맞추는 데 도움을 줍니다.  
  
#### 키보드 탐색에 맞춤선을 사용하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌어 옵니다.  폼의 왼쪽 위 모퉁이에 배치합니다.  
  
2.  Ctrl\+아래쪽 화살표 키를 누릅니다.  컨트롤은 첫 번째로 사용 가능한 가로 맞춤 위치로 폼을 이동합니다.  
  
3.  컨트롤이 폼의 아래쪽에 도달할 때까지 Ctrl\+아래쪽 화살표 키를 누릅니다.  폼 아래로 이동될 때 컨트롤의 위치를 확인합니다.  
  
4.  Ctrl\+오른쪽 화살표 키를 누릅니다.  컨트롤은 첫 번째로 사용 가능한 세로 맞춤 위치로 폼을 이동합니다.  
  
5.  컨트롤이 폼의 한 쪽에 도달할 때까지 Ctrl\+오른쪽 화살표 키를 누릅니다.  컨트롤이 폼으로 이동될 때 컨트롤의 위치를 확인합니다.  
  
6.  화살표 키 조합을 사용하여 컨트롤을 폼 주위로 이동합니다.  컨트롤의 위치와 해당 맞춤선을 확인합니다.  
  
7.  픽셀 하나씩 늘려서 <xref:System.Windows.Forms.Button> 컨트롤의 크기를 조정하려면 Shift\+임의의 화살표 키를 누릅니다.  
  
8.  맞춤선을 늘려 <xref:System.Windows.Forms.Button> 컨트롤의 크기를 조정하려면 Ctrl\+Shift\+임의의 화살표 키를 누릅니다.  
  
## 맞춤선 및 레이아웃 패널  
 맞춤선은 레이아웃 패널 내에서 사용되지 않습니다.  
  
#### 맞춤선을 선택적으로 해제하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  **도구 상자**에서 <xref:System.Windows.Forms.Button> 컨트롤 아이콘을 두 번 클릭합니다.  새 단추 컨트롤이 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 첫 번째 셀에 나타납니다.  
  
3.  두 번 더 **도구 상자**에서 <xref:System.Windows.Forms.Button> 컨트롤 아이콘을 두 번 클릭합니다.  이렇게 하면 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 빈 셀이 하나만 남게 됩니다.  
  
4.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 빈 셀로 끌어 옵니다.  맞춤선이 나타나지 않습니다.  
  
5.  <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 밖으로 끈 다음 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 주위로 이동합니다.  맞춤선이 다시 나타납니다.  
  
## 맞춤선 해제  
 맞춤선은 기본적으로 설정됩니다.  맞춤선을 선택적으로 해제하거나 디자인 환경에서 해제할 수 있습니다.  
  
#### 맞춤선을 선택적으로 해제하려면  
  
-   Alt 키를 누른 채 컨트롤을 폼 주위로 이동합니다.  
  
     맞춤선이 나타나지 않고 컨트롤이 가능한 맞춤 위치에 맞춰지지 않습니다.  
  
#### 디자인 환경에서 맞춤선을 해제하려면  
  
1.  **도구** 메뉴에서 **옵션** 대화 상자를 엽니다.  Windows Forms 디자이너 대화 상자가 열립니다.  자세한 내용은 [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8dd170af-72f0-4212-b04b-034ceee92834)을 참조하십시오.  
  
2.  **일반** 노드를 선택합니다.  **LayoutMode** 섹션에서 **SnapLines**에서 **SnapToGrid**로 선택 사항을 변경합니다.  
  
3.  확인을 클릭하여 설정을 적용합니다.  
  
4.  폼에서 컨트롤을 선택하여 다른 컨트롤 주위로 이동합니다.  맞춤선이 나타나지 않습니다.  
  
## 다음 단계  
 맞춤선을 사용하면 간단하게 폼에 컨트롤을 맞출 수 있습니다.  다음과 같은 제안을 따르는 것이 좋습니다.  
  
-   다른 <xref:System.Windows.Forms.GroupBox> 컨트롤 내에 <xref:System.Windows.Forms.GroupBox> 컨트롤을 중첩해 보십시오.  <xref:System.Windows.Forms.Button> 컨트롤을 자식 <xref:System.Windows.Forms.GroupBox> 컨트롤에 배치하고 다른 컨트롤을 부모 <xref:System.Windows.Forms.GroupBox> 컨트롤에 배치합니다.  <xref:System.Windows.Forms.Button> 컨트롤을 이동하여 맞춤선이 컨테이너 경계와 어떻게 교차하는지 확인합니다.  
  
-   <xref:System.Windows.Forms.TextBox> 컨트롤 열 및 해당 <xref:System.Windows.Forms.Label> 컨트롤 열을 만듭니다.  <xref:System.Windows.Forms.Label>컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 설정합니다.  맞춤선을 사용하여 표시된 텍스트가 <xref:System.Windows.Forms.TextBox> 컨트롤의 텍스트에 맞춰지도록 <xref:System.Windows.Forms.Label>컨트롤을 이동합니다.  
  
 Windows 사용자 인터페이스 디자인에 대한 자세한 내용은 서적 *Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers* Redmond, WA: Microsoft Press, 1999.  \(USBN: 0\-7356\-0566\-1\)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Design.Behavior.SnapLine>   
 [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)   
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)