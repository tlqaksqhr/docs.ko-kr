---
title: My.Forms 개체
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 4d6bb371b13dfb3fb735223b2a6a6a35e1416593
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="myforms-object"></a>My.Forms 개체
현재 프로젝트에 선언 된 각 Windows form의 인스턴스에 액세스 하기 위한 속성을 제공 합니다.  
  
## <a name="remarks"></a>설명  
 `My.Forms` 개체는 현재 프로젝트에 각 폼의 인스턴스를 제공 합니다. 속성의 이름 속성에 액세스 하는 폼의 이름과 같습니다.   
  
 제공한 폼에 액세스할 수 있습니다는 `My.Forms` 한정 하지 않고 폼의 이름을 사용 하 여 개체입니다. 동일 하기 때문에 속성 이름에서 폼의 형식 이름으로, 이렇게 하면 기본 인스턴스가 이전의 처럼 폼에 액세스할 수 있습니다. 예를 들어 `My.Forms.Form1.Show`은 `Form1.Show`와 같습니다.  
  
 `My.Forms` 개체는 현재 프로젝트와 관련 된 양식에을 제공 합니다. 참조 된 Dll에 선언 된 폼에 대 한 액세스를 제공 하지 않습니다. DLL을 제공 하는 폼에 액세스 하려면로 작성 된 폼의 정규화 된 이름을 사용 해야 *DllName*. *생략*합니다.  
  
 사용할 수는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> 속성 응용 프로그램의 모든 열려 있는 폼의 컬렉션을 가져옵니다.  
  
 개체와 해당 속성은 Windows 응용 프로그램에만 사용할 수 있습니다.  
  
## <a name="properties"></a>속성  
 각 속성은 `My.Forms` 개체는 현재 프로젝트에 폼의 인스턴스에 대 한 액세스를 제공 합니다. 속성의 이름 속성에 액세스 하는 폼의 이름과 동일 이며 속성 형식은 폼의 형식과 동일 합니다.  
  
> [!NOTE]
>  이름 충돌이 발생 하는 경우 폼에 액세스할 수 속성 이름이 *RootNamespace*_*Namespace*\_*생략*합니다. 예를 들어 이라는 두 개의 폼 `Form1.`루트 네임 스페이스에 다음이 형식 중 하나가 것 `WindowsApplication1` 및 네임 스페이스에 `Namespace1`, 해당 폼을 통해 액세스 하는 것 `My.Forms.WindowsApplication1_Namespace1_Form1`합니다.  
  
 `My.Forms` 개체는 시작 시에 생성 된 응용 프로그램의 기본 폼의 인스턴스에 대 한 액세스를 제공 합니다. 다른 모든 폼에 대 한는 `My.Forms` 개체에 액세스 하 고 저장할 때 폼의 새 인스턴스를 만듭니다. 해당 속성에 액세스 하는 후속 시도 폼의 해당 인스턴스를 반환 합니다.  
  
 할당 하 여 폼의 삭제할 수 있습니다 `Nothing` 해당 폼에 대 한 속성에 있습니다. 속성 setter 호출은 <xref:System.Windows.Forms.Form.Close%2A> 메서드는 폼의 다음 할당 `Nothing` 은 저장 된 값입니다. 이외의 모든 값을 할당 하는 경우 `Nothing` 속성 setter를 throw 한 <xref:System.ArgumentException> 예외입니다.  
  
 속성이 있는지 여부를 테스트할 수 있습니다는 `My.Forms` 개체를 사용 하 여 폼의 인스턴스는 저장 된 `Is` 또는 `IsNot` 연산자입니다. 이러한 연산자를 사용 하 여 속성의 값이 인지 확인 하기 `Nothing`합니다.  
  
> [!NOTE]
>  일반적으로 `Is` 또는 `IsNot` 연산자에는 비교를 수행 하는 속성의 값을 읽을 수 있습니다. 그러나 현재 저장 하는 경우 `Nothing`, 속성 폼의 새 인스턴스를 만들고 다음 해당 인스턴스를 반환 합니다. Visual Basic 컴파일러의 속성을 처리 하는 반면는 `My.Forms` 알리고 다르게 개체는 `Is` 또는 `IsNot` 연산자를 해당 값을 변경 하지 않고 속성의 상태를 확인 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 기본 제목을 변경 `SidebarMenu` 폼입니다.  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 이 예제가 작동 하려면 프로젝트 라는 폼 있어야 `SidebarMenu`합니다.  
  
 이 코드는 Windows 응용 프로그램 프로젝트에만 작동 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="availability-by-project-type"></a>프로젝트 형식에 따라 가용성  
  
|프로젝트 형식|사용 가능|  
|---|---|  
|Windows 응용 프로그램|**예**|  
|클래스 라이브러리|아니요|  
|콘솔 응용 프로그램|아니요|  
|Windows 컨트롤 라이브러리|아니요|  
|웹 컨트롤 라이브러리|아니요|  
|Windows 서비스|아니요|  
|웹 사이트|아니요|  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [개체](../../../visual-basic/language-reference/objects/index.md)  
 [Is 연산자](../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [응용 프로그램 폼 액세스](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
