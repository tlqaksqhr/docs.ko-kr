---
title: '방법: 바인딩된 컨트롤 만들기 및 표시된 데이터 형식 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: 9055ec9c4b646e0c86819e4e72db8ce20086bace
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542212"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a>방법: 바인딩된 컨트롤 만들기 및 표시된 데이터 형식 지정
Windows Forms 데이터 바인딩 사용 하 여 데이터 바인딩된 컨트롤에 표시 되는 데이터의 서식을 지정할 수 있습니다는 **서식 지정 및 고급 바인딩** 대화 상자.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a>컨트롤을 바인딩하고 표시된 데이터의 서식을 지정하려면 다음을 수행합니다.  
  
1.  데이터 소스에 연결합니다.  
  
     자세한 내용은 참조 [데이터 원본에 연결할](../../../docs/framework/data/adonet/connecting-to-a-data-source.md)합니다.  
  
2.  폼에서 컨트롤을 선택하고 속성 창을 엽니다.  
  
3.  확장 된 **(DataBindings)** 속성을 선택한 다음는 **(고급)** 상자에서 줄임표 단추를 클릭 (![VisualStudioEllipsesButton 스크린 샷] (../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) 표시 하는 **서식 지정 및 고급 바인딩** 해당 컨트롤에 대 한 속성의 전체 목록이 들어 있는 대화 상자.  
  
4.  클릭 하 고 바인딩할 속성 선택 하 고 **바인딩** 화살표입니다.  
  
     사용 가능한 데이터 소스 목록이 표시됩니다.  
  
5.  원하는 단일 데이터 요소를 찾을 때까지 바인딩할 데이터 소스를 확장합니다.  
  
     예를 들어 데이터 집합의 테이블에서 열 값에 바인딩할 경우 데이터 집합 이름을 확장하고 나서 테이블을 이름을 확장하여 열 이름을 표시합니다.  
  
6.  바인딩할 요소 이름을 클릭합니다.  
  
7.  에 **형식의 서식을** 상자 컨트롤에 표시 되는 데이터에 적용할 형식을 클릭 합니다.  
  
     모든 경우에 데이터 소스에 <xref:System.DBNull>이 있으면 컨트롤에 표시된 값을 지정할 수 있습니다. 그러지 않으면 선택한 형식 유형에 따라 옵션이 약간 달라집니다. 다음 표에서는 형식 유형 및 옵션을 보여 줍니다.  
  
    |형식 유형|서식 지정 옵션|  
    |-----------------|-----------------------|  
    |서식 없음|옵션 없음.|  
    |Numeric|소수 자릿수를 사용 하 여 지정 **소수 자릿수** up-down 컨트롤입니다.|  
    |통화|소수 자릿수를 사용 하 여 지정 **소수 자릿수** up-down 컨트롤입니다.|  
    |날짜 시간|에 항목 중 하나를 선택 하 여 날짜 및 시간을 표시할 방법을 선택은 **형식** 선택 상자.|  
    |지수|소수 자릿수를 사용 하 여 지정 **소수 자릿수** up-down 컨트롤입니다.|  
    |사용자 지정|사용자 지정 서식 문자열 사용을 지정합니다.<br /><br /> 자세한 내용은 [서식 지정 형식](../../../docs/standard/base-types/formatting-types.md)을 참조하세요. **참고:** 사용자 지정 형식 문자열은 데이터 소스와 바인딩된 컨트롤 간에 성공적으로 왕복 시간이 보장 되지 않습니다. 대신에 바인딩에 대한 <xref:System.Windows.Forms.Binding.Parse> 또는 <xref:System.Windows.Forms.Binding.Format> 이벤트를 처리하고 이벤트 처리 코드에 사용자 지정 서식 지정을 적용합니다.|  
  
8.  클릭 **확인** 를 닫으려면는 **서식 지정 및 고급 바인딩** 대화 상자 및 속성 창으로 돌아갑니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Windows Form에 단순 바인딩된 컨트롤 만들기](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [Windows Forms에서 사용자 입력 유효성 검사](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)
