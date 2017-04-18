---
title: "Windows Forms에서 지원하는 데이터 소스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "배열[Windows Forms]"
  - "컬렉션[Windows Forms], 바인딩"
  - "데이터[Windows Forms], 데이터 공급자"
  - "데이터 공급자[Windows Forms]"
  - "데이터 소스[Windows Forms]"
  - "DataColumn 클래스"
  - "DataSet 클래스, 바인딩 및 Windows Forms"
  - "DataTable 클래스, 바인딩 및 Windows Forms"
  - "DataView 클래스, 바인딩 및 Windows Forms"
  - "DataViewManager 클래스, 바인딩 및 Windows Forms"
  - "OLE DB 공급자, Windows Forms"
  - "Windows Forms, 데이터 바인딩"
  - "Windows Forms, 소스 데이터"
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Windows Forms에서 지원하는 데이터 소스
기존에는 데이터 바인딩이 응용 프로그램 안에서 데이터베이스에 저장된 데이터를 이용하는 데 사용되었습니다.  Windows Form 데이터 바인딩을 사용하면 최소한의 요구 사항이 충족되는 경우 데이터베이스의 데이터에 액세스할 수 있을 뿐 아니라 배열 및 컬렉션과 같이 다른 구조에 있는 데이터에도 액세스할 수 있습니다.  
  
## 바인딩할 구조  
 Windows Forms에서는 단순한 개체\(단순 바인딩\)부터 ADO.NET 데이터 테이블과 같은 복잡한 목록\(복합 바인딩\)에 이르기까지 다양한 구조에 바인딩할 수 있습니다.  단순 바인딩의 경우 Windows Forms에서는 단순 개체의 공용 속성에 대한 바인딩을 지원합니다.  Windows Forms 목록 기반 바인딩을 수행하려면 일반적으로 개체에서 <xref:System.Collections.IList> 인터페이스나 <xref:System.ComponentModel.IListSource> 인터페이스를 지원해야 합니다.  또한 <xref:System.Windows.Forms.BindingSource> 구성 요소를 통해 바인딩하는 경우에는 <xref:System.Collections.IEnumerable> 인터페이스를 지원하는 개체에 바인딩할 수 있습니다.  데이터 바인딩과 관련된 인터페이스에 대한 자세한 내용은 [데이터 바인딩과 관련된 인터페이스](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)를 참조하십시오.  
  
 다음 목록은 Windows Forms에서 바인딩할 수 있는 구조를 보여 줍니다.  
  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingSource>는 데이터 소스와 Windows Forms 컨트롤 간의 프록시로 사용되는 가장 일반적인 Windows Forms 데이터 소스입니다.  <xref:System.Windows.Forms.BindingSource>의 일반적인 사용 패턴은 컨트롤을 <xref:System.Windows.Forms.BindingSource>에 바인딩한 다음 <xref:System.Windows.Forms.BindingSource>를 데이터 소스\(예: ADO.NET 데이터 테이블 또는 비즈니스 개체\)에 바인딩하는 것입니다.  <xref:System.Windows.Forms.BindingSource>는 데이터 바인딩 지원을 사용할 수 있도록 하고 지원 수준을 높여 주는 서비스를 제공합니다.  예를 들어, <xref:System.Windows.Forms.DataGridView> 및 <xref:System.Windows.Forms.ComboBox>와 같은 Windows Forms 목록 기반 컨트롤은 <xref:System.Collections.IEnumerable> 데이터 소스에 대한 바인딩을 직접 지원하지 않지만 <xref:System.Windows.Forms.BindingSource>를 통해 바인딩함으로써 이 시나리오를 수행할 수 있습니다.  이 경우 <xref:System.Windows.Forms.BindingSource>는 데이터 소스를 <xref:System.Collections.IList>로 변환합니다.  
  
 단순 개체  
 Windows Forms에서는 <xref:System.Windows.Forms.Binding> 형식을 사용하여 개체 인스턴스의 공용 속성에 컨트롤 속성을 데이터 바인딩할 수 있습니다.  또한 Windows Forms에서는 <xref:System.Windows.Forms.BindingSource>를 사용할 경우 <xref:System.Windows.Forms.ListControl>과 같은 목록 기반 컨트롤을 개체 인스턴스에 바인딩할 수 있습니다.  
  
 배열 또는 컬렉션  
 데이터 소스로 작동하려면 목록에서 <xref:System.Collections.IList> 인터페이스를 구현해야 합니다. 예를 들면 <xref:System.Array> 클래스의 인스턴스인 배열이 있습니다.  배열에 대한 자세한 내용은 [How to: Create an Array of Objects \(Visual Basic\)](http://msdn.microsoft.com/ko-kr/6b64e069-0387-400c-9081-3bdc581020c3)을 참조하십시오.  
  
 일반적으로 데이터 바인딩을 위한 개체의 목록을 만들 때는 <xref:System.ComponentModel.BindingList%601>을 사용합니다.  <xref:System.ComponentModel.BindingList%601>은 <xref:System.ComponentModel.IBindingList> 인터페이스의 제네릭 버전입니다.  <xref:System.ComponentModel.IBindingList> 인터페이스는 양방향 데이터 바인딩에 필요한 속성, 메서드 및 이벤트를 추가하여 <xref:System.Collections.IList> 인터페이스를 확장합니다.  
  
 <xref:System.Collections.IEnumerable>  
 Windows Forms 컨트롤은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 통해 바인딩된 경우 <xref:System.Collections.IEnumerable> 인터페이스만 지원하는 데이터 소스에 바인딩될 수 있습니다.  
  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] 데이터 개체  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]에서는 바인딩 대상으로 사용하기에 적합한 데이터 구조를 많이 제공합니다.  각 구조에 따라 복잡성이 다릅니다.  
  
-   <xref:System.Data.DataColumn>.  여러 열이 하나의 테이블을 구성한다는 점에서 <xref:System.Data.DataColumn>은 <xref:System.Data.DataTable>의 필수 빌딩 블록입니다.  각 <xref:System.Data.DataColumn>은 열에 저장되는 데이터 종류\(예: 차를 설명하는 테이블에 있는 자동차의 종류\)를 결정하는 <xref:System.Data.DataColumn.DataType%2A> 속성을 갖습니다.  컨트롤\(예: <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성\)을 데이터 테이블 안에 있는 열에 단순 바인딩할 수 있습니다.  
  
-   <xref:System.Data.DataTable>.  <xref:System.Data.DataTable>은 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]에서 행과 열이 있는 테이블을 나타냅니다.  데이터 테이블에는 두 개의 컬렉션이 포함됩니다. <xref:System.Data.DataColumn>은 주어진 테이블에 있는 데이터의 열을 나타내는데 이 열은 해당 테이블에 입력될 수 있는 데이터 종류를 결정합니다. <xref:System.Data.DataRow>는 주어진 테이블에 있는 데이터 행을 나타냅니다.  컨트롤을 데이터 테이블에 포함된 정보에 복합 바인딩\(예: <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 테이블에 바인딩\)할 수 있습니다.  그러나 <xref:System.Data.DataTable>에 바인딩할 경우 실제로는 테이블의 기본 뷰에 바인딩됩니다.  
  
-   <xref:System.Data.DataView>.  <xref:System.Data.DataView>는 필터링 또는 정렬될 수 있는 단일 데이터 테이블에 대한 사용자 지정 뷰입니다.  데이터 뷰는 복합 바인딩된 컨트롤에서 사용하는 데이터 "스냅숏"입니다.  데이터 뷰 안에 있는 데이터에 단순 바인딩 또는 복합 바인딩할 수 있지만 이것은 업데이트될 수 있는 완전한 데이터 소스에 바인딩되는 것이 아니라 데이터의 고정된 "화면"에 바인딩되는 것입니다.  
  
-   <xref:System.Data.DataSet>.  <xref:System.Data.DataSet>은 데이터베이스에 있는 데이터에 대한 테이블, 관계 및 제약 조건의 컬렉션입니다.  데이터 집합 안에 있는 데이터에 단순 바인딩 또는 복합 바인딩할 수 있지만 이것은 <xref:System.Data.DataSet>의 기본 <xref:System.Data.DataViewManager>에 바인딩되는 것입니다\(다음 글머리 기호 참조\).  
  
-   <xref:System.Data.DataViewManager>.  <xref:System.Data.DataViewManager>는 전체 <xref:System.Data.DataSet>에 대한 사용자 지정 뷰이며, <xref:System.Data.DataView>와 비슷하지만 관계가 포함됩니다.  <xref:System.Data.DataViewManager.DataViewSettings%2A> 컬렉션을 사용하면 주어진 테이블에 대해 <xref:System.Data.DataViewManager>에서 가지고 있는 모든 뷰에 기본 필터와 정렬 옵션을 설정할 수 있습니다.  
  
## 참고 항목  
 [Windows Forms 데이터 바인딩의 변경 알림](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [데이터 바인딩 및 Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)