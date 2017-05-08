---
title: "DataGridView 컨트롤 시나리오(Windows Forms) | Microsoft Docs"
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
  - "데이터[Windows Forms], 표 형식으로 표시"
  - "데이터 표, 데이터 표 정보"
  - "DataGridView 컨트롤[Windows Forms], 시나리오"
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# DataGridView 컨트롤 시나리오(Windows Forms)
<xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하면 다양한 데이터 소스의 표 형식 데이터를 표시할 수 있습니다.  간단하게 사용하는 경우 <xref:System.Windows.Forms.DataGridView>를 수동으로 채운 다음 컨트롤을 통해 데이터를 직접 조작할 수 있습니다.  그러나 대개는 외부 데이터 소스에 데이터를 저장한 다음 <xref:System.Windows.Forms.BindingSource> 구성 요소를 통해 컨트롤을 데이터 소스에 바인딩합니다.  
  
 이 항목에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤과 관련된 몇 가지 일반적인 시나리오를 설명합니다.  
  
## 시나리오 1: 소량의 데이터 표시  
 데이터를 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시할 때 외부 데이터 소스에 데이터를 저장하지 않아도 됩니다.  소량의 데이터를 사용하는 경우에는 컨트롤을 직접 채운 다음 컨트롤을 통해 데이터를 조작할 수 있습니다.  이것을 *바인딩되지 않은 모드*라고 합니다.  자세한 내용은 [방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)를 참조하십시오.  
  
### 시나리오 주요 사항  
  
-   바인딩되지 않은 모드에서는 컨트롤을 수동으로 채웁니다.  
  
-   바인딩되지 않은 모드는 특히 소량의 읽기 전용 데이터에 적합합니다.  
  
-   바인딩되지 않은 모드는 스프레드시트 모양의 표나 낮은 밀도로 채워진 표에도 적합합니다.  
  
## 시나리오 2: 외부 데이터 소스에 저장된 데이터 보기 및 업데이트  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터베이스 테이블이나 비즈니스 개체 컬렉션과 같은 데이터 소스에 저장된 데이터에 액세스할 수 있는 UI\(사용자 인터페이스\)로 사용할 수 있습니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
### 시나리오 주요 사항  
  
-   바인딩된 모드를 사용하면 데이터 소스에 연결한 다음 데이터 소스 속성이나 데이터베이스 열을 기반으로 자동으로 열을 만들고 컨트롤을 채울 수 있습니다.  
  
-   바인딩된 모드는 데이터에 대한 사용자 상호 작용이 많은 경우에 적합합니다.  데이터에 표시 형식을 지정할 수 있으며 사용자 지정 데이터를 데이터 소스에 필요한 형식으로 구문 분석할 수 있습니다.  데이터 입력 서식 오류 및 데이터베이스 제약 조건 오류를 감지하여 사용자에게 경고를 보내고 오류가 있는 셀을 수정하도록 할 수 있습니다.  
  
-   열 정렬, 고정 및 다시 정렬과 같은 추가 기능을 통해 사용자는 워크플로에 가장 적합한 방식으로 데이터를 볼 수 있습니다.  
  
-   클립보드 지원을 통해 사용자는 응용 프로그램에서 다른 응용 프로그램으로 데이터를 복사할 수 있습니다.  
  
## 시나리오 3: 고급 데이터  
 표준 데이터 바인딩 모델로는 처리할 수 없는 작업이 있는 경우에는 *가상 모드*를 구현하여 컨트롤과 데이터의 상호 작용을 관리할 수 있습니다.  가상 모드를 구현한다는 것은 정보가 필요할 때 컨트롤에서 셀 정보를 요청할 수 있도록 하나 이상의 이벤트 처리기를 구현하는 것을 의미합니다.  
  
 예를 들어, 많은 양의 데이터 작업을 수행해야 하는 경우 최적의 효율성을 얻기 위해 가상 모드를 구현할 수 있습니다.  또한 가상 모드는 다른 데이터 소스에서 검색한 열과 함께 표시할 바인딩되지 않은 열의 값을 유지하는 데 유용합니다.  
  
 가상 모드에 대한 자세한 내용은 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)을 참조하십시오.  
  
### 시나리오 주요 사항  
  
-   가상 모드는 성능을 세부적으로 조정해야 하는 대량의 데이터를 표시하는 데 적합합니다.  
  
## 시나리오 4: 열 및 행의 크기를 자동으로 조정  
 정기적으로 업데이트되는 데이터를 표시할 때 모든 내용이 표시되도록 행과 열의 크기를 자동으로 조정할 수 있습니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤에는 수동으로 크기를 조정하거나, 특정한 경우에 프로그래밍 방식으로 크기를 조정하거나, 내용이 바뀔 때마다 자동으로 크기를 조정할 수 있는 여러 가지 옵션이 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
### 시나리오 주요 사항  
  
-   수동 크기 조정을 통해 셀 높이와 너비를 조정할 수 있습니다.  
  
-   자동 크기 조정을 통해 셀 내용이 잘리지 않도록 셀 크기를 유지할 수 있습니다.  
  
-   연속된 자동 크기 조정으로 인한 성능 저하를 방지하기 위해 프로그래밍 방식의 크기 조정을 통해 특정 시간에 크기를 조정할 수 있습니다.  
  
## 시나리오 5: 간단한 사용자 정의  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에는 컨트롤의 기본 모양과 동작을 변경할 수 있는 여러 가지 방법이 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
### 시나리오 주요 사항  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 사용하면 컨트롤의 여러 단계와 개별 요소에 대한 색, 글꼴, 서식 및 위치 정보를 제공할 수 있습니다.  
  
-   여러 요소에서 셀 스타일을 계층화하고 공유하여 코드를 재사용할 수 있습니다.  
  
## 시나리오 6: 고급 사용자 지정  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에는 컨트롤의 모양과 동작을 사용자 지정할 수 있는 여러 가지 방법이 있습니다.  
  
### 시나리오 주요 사항  
  
-   고유한 셀 그리기 코드를 제공할 수 있습니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)을 참조하십시오.  
  
-   고유한 행 그리기 기능을 제공할 수 있습니다.  예를 들어, 이 기능은 여러 열에 확장된 내용으로 행을 만드는 데 유용합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)을 참조하십시오.  
  
-   자체의 셀 및 열 클래스를 구현하여 셀 모양을 사용자 지정할 수 있습니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 동작 및 모양을 확장하여 셀과 열 사용자 지정](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)을 참조하십시오.  
  
-   자체의 셀 및 열 클래스를 구현하여 기본 제공 열 형식에서 제공하는 컨트롤 이외의 컨트롤을 호스팅할 수 있습니다.  자세한 내용은 [방법: Windows Forms DataGridView 셀에서 컨트롤 호스팅](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 [DataGridView 컨트롤 개요](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)