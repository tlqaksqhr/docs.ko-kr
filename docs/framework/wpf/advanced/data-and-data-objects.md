---
title: "데이터 및 데이터 개체 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "데이터 전송[WPF], 끌어서 놓기"
  - "DataFormats 클래스[WPF]"
  - "DataObject 클래스[WPF]"
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 데이터 및 데이터 개체
끌어서 놓기 작업의 일부로 전송되는 데이터는 데이터 개체에 저장됩니다.  개념적으로 보면 데이터 개체는 다음 쌍 중 하나 이상으로 구성됩니다.  
  
-   실제 데이터가 포함된 <xref:System.Object>  
  
-   해당 데이터 형식 식별자  
  
 데이터 자체는 기본 <xref:System.Object>로 나타낼 수 있는 모든 것으로 구성될 수 있습니다.  해당 데이터 형식은 데이터의 형식에 대한 힌트를 제공하는 문자열 또는 <xref:System.Type>입니다.  데이터 개체에는 여러 데이터\/데이터 형식 쌍에 대한 호스팅이 지원됩니다. 따라서 단일 데이터 개체가 여러 형식의 데이터를 제공할 수 있습니다.  
  
<a name="Data_and_Data_Objects"></a>   
## 데이터 개체  
 모든 데이터 개체는 데이터 전송을 사용 가능 및 용이하게 하는 다음 표준 메서드 집합을 제공하는 <xref:System.Windows.IDataObject> 인터페이스를 구현해야 합니다.  
  
|메서드|요약|  
|---------|--------|  
|<xref:System.Windows.IDataObject.GetData%2A>|지정된 데이터 형식의 데이터 개체를 검색합니다.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|지정된 형식의 데이터가 있거나 지정된 형식으로 변환될 수 있는지 확인합니다.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|이 데이터 개체의 데이터가 저장되거나 변환될 수 있는 형식 목록을 반환합니다.|  
|<xref:System.Windows.IDataObject.SetData%2A>|이 데이터 개체에 지정된 데이터를 저장합니다.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 <xref:System.Windows.DataObject> 클래스에서 <xref:System.Windows.IDataObject>의 기본 구현을 제공합니다.  스톡 <xref:System.Windows.DataObject> 클래스는 대부분의 일반 데이터 전송 시나리오에 충분합니다.  
  
 비트맵, CSV, 파일, HTML, RTF, 문자열, 텍스트, 오디오 등의 미리 정의된 여러 형식이 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공되는 미리 정의된 데이터 형식에 대한 자세한 내용은 <xref:System.Windows.DataFormats> 클래스 참조 항목을 참조하십시오.  
  
 일반적으로 데이터 개체에는 데이터를 추출하는 동안 한 형식으로 저장된 데이터를 다른 형식으로 자동 변환하는 기능이 포함되어 있습니다. 이 기능을 자동 변환이라고 합니다.  데이터 개체에서 사용할 수 있는 데이터 형식을 쿼리할 경우 <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> 또는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 메서드를 호출하고 `autoConvert` 매개 변수를 `false`로 지정하여 자동 변환할 수 있는 데이터 형식을 네이티브 데이터 형식으로 필터링할 수 있습니다.  <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> 메서드를 사용하여 데이터를 데이터 개체에 추가할 경우 `autoConvert` 매개 변수를 `false`로 설정하여 데이터의 자동 변환을 방지할 수 있습니다.  
  
<a name="Working_with_Data_Objects"></a>   
## 데이터 개체 작업  
 이 단원에서는 데이터 개체 만들기 및 작업을 위한 일반적인 기술에 대해 설명합니다.  
  
### 새 데이터 개체 만들기  
 <xref:System.Windows.DataObject> 클래스는 새 <xref:System.Windows.DataObject> 인스턴스를 단일 데이터\/데이터 형식 쌍으로 쉽게 채울 수 있게 하는 여러 오버로드된 생성자를 제공합니다.  
  
 다음 예제 코드에서는 새 데이터 개체를 만들고 오버로드된 생성자 <xref:System.Windows.DataObject.%23ctor%2A>\(<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>\) 중 하나를 사용하여 문자열 및 지정된 데이터 형식으로 데이터 개체를 초기화합니다.  이 경우 데이터 형식은 문자열로 지정되며 <xref:System.Windows.DataFormats> 클래스는 미리 정의된 형식 문자열 집합을 제공합니다.  저장된 데이터는 기본적으로 자동 변환됩니다.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 데이터 개체를 만드는 추가 코드 예제는 [데이터 개체 만들기](../../../../docs/framework/wpf/advanced/how-to-create-a-data-object.md)를 참조하십시오.  
  
### 데이터를 여러 형식으로 저장  
 단일 데이터 개체에서 데이터를 여러 형식으로 저장할 수 있습니다.  단일 데이터 개체에서 여러 데이터 형식을 전략적으로 사용하면 단일 데이터 형식만 표시할 수 있는 경우보다 다양한 놓기 대상에서 데이터 개체를 사용할 수 있습니다.  일반적으로 끌기 소스는 잠재적 놓기 대상에서 사용할 수 있는 데이터 형식과 무관해야 합니다.  
  
 다음 예제에서는 <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> 메서드를 사용하여 데이터를 여러 형식으로 데이터 개체에 추가하는 방법을 보여 줍니다.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### 데이터 개체에서 사용할 수 있는 형식 쿼리  
 단일 데이터 개체가 데이터 형식을 개수에 상관없이 포함할 수 있으므로 데이터 개체에는 사용할 수 있는 데이터 형식 목록을 검색하는 기능이 포함되어 있습니다.  
  
 다음 예제 코드에서는 <xref:System.Windows.DataObject.GetFormats%2A> 오버로드를 사용하여 데이터 개체에서 기본적으로 및 자동 변환을 통해 사용할 수 있는 모든 데이터 형식을 나타내는 문자열 배열을 가져옵니다.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 데이터 개체에서 사용할 수 있는 데이터 형식을 쿼리하는 추가 코드 예제는 [데이터 개체의 데이터 형식 나열](../../../../docs/framework/wpf/advanced/how-to-list-the-data-formats-in-a-data-object.md)을 참조하십시오.  데이터 개체에서 특정 데이터 형식의 존재를 쿼리하는 예제는 [데이터 개체에 데이터 형식이 있는지 확인](../../../../docs/framework/wpf/advanced/how-to-determine-if-a-data-format-is-present-in-a-data-object.md)을 참조하십시오.  
  
### 데이터 개체에서 데이터 검색  
 데이터 개체에서 특정 형식의 데이터를 검색하는 작업에서는 단순히 <xref:System.Windows.DataObject.GetData%2A> 메서드 중 하나를 호출하고 원하는 데이터 형식을 지정합니다.  <xref:System.Windows.DataObject.GetDataPresent%2A> 메서드 중 하나를 사용하여 특정 데이터 형식의 존재를 확인할 수 있습니다.  <xref:System.Windows.DataObject.GetData%2A>는 <xref:System.Object>의 데이터를 반환합니다. 데이터 형식에 따라 이 개체는 형식별 컨테이너에 캐스팅될 수 있습니다.  
  
 다음 예제 코드에서는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> 오버로드를 사용하여 지정된 데이터 형식을 사용할 수 있는지\(기본적으로 또는 자동 변환에 의해\) 여부를 확인합니다.  지정된 형식을 사용할 수 있는 경우 이 예제는 <xref:System.Windows.DataObject.GetData%28System.String%29> 메서드를 사용하여 데이터를 검색합니다.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 데이터 개체에서 데이터를 검색하는 추가 코드 예제는 [특정 데이터 형식의 데이터 검색](../../../../docs/framework/wpf/advanced/how-to-retrieve-data-in-a-particular-data-format.md)을 참조하십시오.  
  
### 데이터 개체에서 데이터 제거  
 데이터를 데이터 개체에서 직접 제거할 수 없습니다.  데이터 개체에서 데이터를 효율적으로 제거하려면 다음 단계를 수행합니다.  
  
1.  보유할 데이터만 포함할 새 데이터 개체를 만듭니다.  
  
2.  이전 데이터 개체에서 새 데이터 개체로 원하는 데이터를 "복사"합니다.  데이터를 복사하려면 <xref:System.Windows.DataObject.GetData%2A> 메서드 중 하나를 사용하여 원시 데이터를 포함하는 <xref:System.Object>를 검색한 다음 <xref:System.Windows.DataObject.SetData%2A> 메서드 중 하나를 사용하여 데이터를 새 데이터 개체에 추가합니다.  
  
3.  이전 데이터 개체를 새 데이터 개체로 바꿉니다.  
  
> [!NOTE]
>  <xref:System.Windows.DataObject.SetData%2A> 메서드는 데이터를 단지 데이터 개체에 추가할 뿐이여 데이터 및 데이터 형식이 이전 호출과 같은 경우에도 데이터를 바꾸지 않습니다.  동일한 데이터 및 데이터 형식에 대해 <xref:System.Windows.DataObject.SetData%2A>를 두 번 호출하면 데이터\/데이터 형식이 데이터 개체에 두 번 존재하게 됩니다.