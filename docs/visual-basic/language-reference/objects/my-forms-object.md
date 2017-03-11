---
title: "My.Forms Object | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "My.Forms"
  - "My.MyProject.Forms"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Forms object"
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# My.Forms Object
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

현재 프로젝트에 선언된 각 Windows Form의 인스턴스에 액세스하기 위한 속성을 제공합니다.  
  
## 설명  
 `My.Forms` 개체는 현재 프로젝트에 있는 각 폼의 인스턴스를 제공합니다.  속성 이름은 속성이 액세스하는 폼의 이름과 동일합니다.  프로젝트에 폼을 추가하는 방법은 [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/ko-kr/3d7bb25f-fd90-47cf-9378-fa0d764686c1)를 참조하십시오.  
  
 한정자 없이 폼 이름을 사용하여 `My.Forms` 개체에서 제공한 폼에 액세스할 수 있습니다.  속성 이름이 폼 형식 이름과 동일하기 때문에 이렇게 하면 기본 인스턴스가 있는 것처럼 폼에 액세스할 수 있습니다.  예를 들어, `My.Forms.Form1.Show`은 `Form1.Show`와 같습니다.  
  
 `My.Forms` 개체는 현재 프로젝트에 연결된 폼만 노출하고  참조된 DLL에서 선언한 폼에 대한 액세스는 제공하지 않습니다.  DLL이 제공하는 폼에 액세스하려면 *DllName*.*FormName* 형식으로 작성된 폼의 정규화된 이름을 사용해야 합니다.  
  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> 속성을 사용하여 모든 응용 프로그램의 열려 있는 폼의 컬렉션을 가져올 수 있습니다.  
  
 개체와 해당 속성은 Windows 응용 프로그램에서만 사용할 수 있습니다.  
  
## 속성  
 `My.Forms` 개체의 각 속성은 현재 프로젝트의 폼 인스턴스에 대한 액세스를 제공합니다.  속성의 이름은 속성이 액세스하는 폼의 이름과 동일하며 속성 형식은 폼의 형식과 동일합니다.  
  
> [!NOTE]
>  이름이 충돌하는 경우 폼에 액세스하기 위한 속성 이름은 *RootNamespace*\_*Namespace*\_*FormName*입니다.  `Form1`이라는 폼이 두 개 있는 경우 이 폼 중 하나가 `WindowsApplication1` 루트 네임스페이스와 `Namespace1` 네임스페이스에 있으면 `My.Forms.WindowsApplication1_Namespace1_Form1`을 통해 해당 폼에 액세스할 수 있습니다.  
  
 `My.Forms` 개체는 시작할 때 만들어진 응용 프로그램 기본 폼의 인스턴스에 대한 액세스를 제공합니다.  다른 모든 폼에 대해 `My.Forms` 개체는 액세스하고 저장할 때 해당 폼의 새 인스턴스를 만듭니다.  다음에 해당 속성에 액세스하려고 시도하는 경우 폼의 인스턴스를 반환합니다.  
  
 해당 폼의 속성에 `Nothing`을 할당해서 폼을 삭제할 수 있습니다.  속성 setter는 폼의 <xref:System.Windows.Forms.Form.Close%2A> 메서드를 호출한 다음 `Nothing`을 저장된 값에 할당합니다.  속성에 `Nothing` 이외의 값을 할당하는 경우 setter는 <xref:System.ArgumentException> 예외를 throw합니다.  
  
 `Is` 또는 `IsNot` 연산자를 사용하여 `My.Forms` 개체의 속성이 폼의 인스턴스를 저장하는지 여부를 테스트할 수 있습니다.  이러한 연산자를 사용하여 속성 값이 `Nothing`인지 확인할 수 있습니다.  
  
> [!NOTE]
>  일반적으로 `Is` 또는 `IsNot` 연산자가 비교를 수행하려면 속성 값을 읽어야 합니다.  하지만 현재 속성이 `Nothing`을 저장하는 경우 속성은 폼의 새 인스턴스를 만든 다음 해당 인스턴스를 반환하고  Visual Basic 컴파일러는 `My.Forms` 개체의 속성을 다르게 처리하여 `Is` 또는 `IsNot` 연산자가 해당 값을 변경하지 않고도 속성 상태를 확인할 수 있게 해 줍니다.  
  
## 예제  
 이 예제에서는 기본 `SidebarMenu` 폼의 제목을 변경합니다.  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/visualbasic/my-forms-object_1.vb)]  
  
 이 예제를 실행하려면 프로젝트에 `SidebarMenu`라는 폼이 있어야 합니다.  자세한 내용은 [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/ko-kr/3d7bb25f-fd90-47cf-9378-fa0d764686c1)를 참조하십시오.  
  
 이 코드는 Windows 응용 프로그램 프로젝트에서만 실행됩니다.  
  
## 요구 사항  
  
### 프로젝트 형식별 사용 가능 여부  
  
|||  
|-|-|  
|프로젝트 형식|사용 가능|  
|Windows 응용 프로그램|**예**|  
|클래스 라이브러리|아니요|  
|콘솔 응용 프로그램|아니요|  
|Windows 컨트롤 라이브러리|아니요|  
|웹 컨트롤 라이브러리|아니요|  
|Windows 서비스|아니요|  
|웹 사이트|아니요|  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>   
 <xref:System.Windows.Forms.Form>   
 <xref:System.Windows.Forms.Form.Close%2A>   
 [Objects](../../../visual-basic/language-reference/objects/index.md)   
 [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/ko-kr/3d7bb25f-fd90-47cf-9378-fa0d764686c1)   
 [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Accessing Application Forms](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)