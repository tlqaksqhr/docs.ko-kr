---
title: 데이터 및 데이터 개체
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data transfer [WPF], drag-and-drop
- DataFormats class [WPF]
- DataObject class [WPF]
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
ms.openlocfilehash: ff596dc7428c9d105a27999f216d33e735e35a22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540321"
---
# <a name="data-and-data-objects"></a>데이터 및 데이터 개체
끌어서 놓기 작업의 일부로 전송 되는 데이터는 데이터 개체에 저장 됩니다.  개념적으로, 데이터 개체를 하나 이상의 다음 쌍으로 구성 됩니다.  
  
-   <xref:System.Object> 하는 실제 데이터를 포함 합니다.  
  
-   해당 데이터 형식 식별자입니다.  
  
 데이터 자체는 기반으로 나타낼 수 있는 아무 것도 구성할 수 있습니다 <xref:System.Object>합니다.  해당 데이터 형식이 문자열인 또는 <xref:System.Type> 에 데이터 형식에 대 한 힌트를 제공 하는입니다.  여러 데이터/데이터 형식 쌍; 호스팅 데이터 개체 지원 이렇게 하면 단일 데이터 개체를 여러 형식에 데이터를 제공 합니다.  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a>데이터 개체  
 모든 데이터 개체를 구현 해야 합니다는 <xref:System.Windows.IDataObject> 인터페이스를 사용 하도록 설정 및 데이터 전송 하는 메서드는 다음과 같은 표준 집합을 제공 합니다.  
  
|메서드|요약|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|지정된 된 데이터 형식에 데이터 개체를 검색 합니다.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|지정 된 형식의 데이터 또는 지정된 된 형식으로 변환할 수 있는지 여부를 확인 합니다.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|이 데이터 개체의 데이터에 저장 되거나으로 변환 될 수 있는 형식 목록을 반환 합니다.|  
|<xref:System.Windows.IDataObject.SetData%2A>|이 데이터 개체에 지정된 된 데이터를 저장 합니다.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기본 구현을 제공 <xref:System.Windows.IDataObject> 에 <xref:System.Windows.DataObject> 클래스입니다. 재고 <xref:System.Windows.DataObject> 클래스는 많은 일반적인 데이터 전송 시나리오에 적합 합니다.  
  
 비트맵, CSV, 파일, HTML, RTF, 문자열, 텍스트, 오디오 등의 몇 가지 미리 정의 된 형식으로 있습니다. 와 함께 제공 되는 미리 정의 된 데이터 형식에 대 한 내용은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 참조는 <xref:System.Windows.DataFormats> 클래스 참조 항목입니다.  
  
 데이터 개체에는 일반적으로 자동으로 데이터를 추출 하는 동안 하나를 다른 형식으로 저장 된 데이터를 변환 하는 기능이 포함 되어 이 기능은 자동 전환 이라고 합니다. 데이터 개체에 사용할 수 있는 데이터 형식에 대 한을 쿼리할 때 자동 변환을 데이터 형식을 필터링 할 수 네이티브 데이터 형식에서 호출 하 여는 <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> 또는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 메서드와 지정 하는 `autoConvert` 매개 변수로 `false`합니다.  데이터와 데이터 개체를 추가할 때의 <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> 데이터 자동 변환 메서드를 설정 하 여 방지할 수 있습니다는 `autoConvert` 매개 변수를 `false`합니다.  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a>데이터 개체 작업  
 이 섹션을 만들고 데이터 개체로 작업 하기 위한 일반적인 방법을 설명 합니다.  
  
### <a name="creating-new-data-objects"></a>새 데이터 개체 만들기  
 <xref:System.Windows.DataObject> 새 채우기 용이 하 게 하는 여러 오버 로드 된 생성자를 제공 하는 클래스 <xref:System.Windows.DataObject> 단일 데이터/데이터 형식 쌍을 사용 하 여 인스턴스.  
  
 다음 코드 예제에서는 새 데이터 개체를 만들고 오버 로드 된 생성자 중 하나를 사용 하 여 <xref:System.Windows.DataObject.%23ctor%2A>(<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) 문자열 및 지정 된 데이터 형식으로 데이터 개체를 초기화 합니다.  데이터 형식은 문자열;에 의해 지정은 경우 <xref:System.Windows.DataFormats> 클래스 미리 정의 된 형식 문자열의 집합을 제공 합니다. 기본적으로 저장 된 데이터의 자동 변환은 허용 됩니다.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 데이터 개체를 만드는 코드의 더 많은 예제를 참조 하십시오. [데이터 개체를 만들](../../../../docs/framework/wpf/advanced/how-to-create-a-data-object.md)합니다.  
  
### <a name="storing-data-in-multiple-formats"></a>여러 형식의 데이터를 저장합니다.  
 단일 데이터 개체는 여러 형식 데이터를에서 저장할 수 있습니다.   전략적 사용 단일 데이터 개체에서 여러 데이터 형식 잠재적으로 하면 데이터 개체 보다 다양 한 보다 놓기 대상으로 하는 경우에 하나의 데이터 형식에 나타낼 수 있습니다.  즉, 일반적으로 끌기 소스 두어서는 안 잠재적인 놓기 대상으로 사용할 수 있는 데이터 형식에 대 한 참고 합니다.  
  
 사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> 메서드 데이터를 여러 형식 데이터 개체를 추가 합니다.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>사용 가능한 형식에 대 한 데이터 개체를 쿼리합니다.  
 단일 데이터 개체 데이터 형식의 임의 개수의 포함할 수 있으므로 사용 가능한 데이터 형식의 목록을 검색 하는 기능이 포함 됩니다.  
  
 다음 예제 코드를 사용 하 여는 <xref:System.Windows.DataObject.GetFormats%2A> 오버 로드를 통해 데이터 개체 (네이티브 및 자동 변환을 통해)에서 사용할 수 있는 모든 데이터 형식을 나타내는 문자열의 배열을 가져옵니다.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 사용 가능한 데이터 형식에 대 한 데이터 개체를 쿼리 하는 코드의 더 많은 예제를 참조 하십시오. [데이터 개체의 데이터 형식 나열](../../../../docs/framework/wpf/advanced/how-to-list-the-data-formats-in-a-data-object.md)합니다.  특정 데이터 형식의 현재 상태에 대 한 데이터 개체를 쿼리하고의 예 참조 [데이터 형식이 있는지 확인 합니다. 데이터 개체에](../../../../docs/framework/wpf/advanced/how-to-determine-if-a-data-format-is-present-in-a-data-object.md)합니다.  
  
### <a name="retrieving-data-from-a-data-object"></a>데이터 개체에서 데이터 검색  
 중 하나를 호출 하면 됩니다 특정 형식의 데이터 개체에서 데이터를 검색 하는 <xref:System.Windows.DataObject.GetData%2A> 메서드 및 원하는 데이터 형식을 지정 합니다.  중 하나는 <xref:System.Windows.DataObject.GetDataPresent%2A> 특정 데이터 형식의 존재를 확인 하려면 메서드를 사용할 수 있습니다.  <xref:System.Windows.DataObject.GetData%2A> 에 데이터를 반환는 <xref:System.Object>; 데이터 형식에 따라이 개체는 특정 형식의 컨테이너도 캐스팅 될 수 있습니다.  
  
 다음 예제 코드를 사용 하 여는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> 오버 로드는 지정 된 데이터 형식을 사용할 수 있는지 확인 하려면 (기본 또는 자동 변환을 통해). 이 예제에서는 지정 된 형식이 있는 경우 사용 하 여 데이터를 검색 된 <xref:System.Windows.DataObject.GetData%28System.String%29> 메서드.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 데이터 개체에서 데이터를 검색 하는 코드의 더 많은 예제를 참조 하십시오. [특정 데이터 형식에 대 한 데이터 검색](../../../../docs/framework/wpf/advanced/how-to-retrieve-data-in-a-particular-data-format.md)합니다.  
  
### <a name="removing-data-from-a-data-object"></a>데이터 개체에서 데이터를 제거합니다.  
 데이터 개체에서 데이터를 직접 제거할 수 없습니다.  데이터에서 데이터 개체를 효과적으로 제거 하려면 다음이 단계를 따르십시오.  
  
1.  유지 하려는 데이터에만 포함 하는 새 데이터 개체를 만듭니다.  
  
2.  "복사" 새 데이터 개체에 이전 데이터 개체에서 원하는 데이터입니다.  데이터를 복사 하려면 중 하나를 사용는 <xref:System.Windows.DataObject.GetData%2A> 검색 하는 메서드는 <xref:System.Object> 원시 데이터를 포함 하 고 다음 중 하나를 사용 하 여는 <xref:System.Windows.DataObject.SetData%2A> 새 데이터 개체에 데이터를 추가 하는 방법입니다.  
  
3.  이전 데이터 개체를 새 항목으로 대체 합니다.  
  
> [!NOTE]
>  <xref:System.Windows.DataObject.SetData%2A> 메서드 데이터 개체에만 데이터를 추가, 데이터 및 데이터 형식 동일 정확히 한 이전 호출 하는 경우에 데이터를 대체 하지 않고 있습니다. 호출 <xref:System.Windows.DataObject.SetData%2A> 동일한 데이터 및 데이터에 대해 두 번 형식 데이터 개체에 두 번 없는 데이터/데이터 형식 발생 합니다.
