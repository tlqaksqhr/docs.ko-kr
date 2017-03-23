---
title: "연습:은 관리 되는 Visual Studio (Visual Basic)에서 어셈블리의 형식 포함 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: adc58e081cd9b874a841d84b11d92cbffb6ba6b8
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a>연습: Visual Studio (Visual Basic)에서 관리 되는 어셈블리의 형식 포함
강력한 이름의 관리 되는 어셈블리의 형식 정보를 포함 하는 경우에 버전 독립성을 달성 하기 위해 응용 프로그램의 형식을 느슨하게 결합 수 있습니다. 즉, 각 버전에 대해 다시 컴파일할 필요 없이 관리 되는 라이브러리의 여러 버전 형식을 사용 하 여 프로그램을 작성할 수 있습니다.  
  
 형식 포함 Microsoft Office에서 자동화 개체를 사용 하는 응용 프로그램과 같은 COM interop에 자주 사용 됩니다. 서로 다른 컴퓨터에 다른 버전의 Microsoft Office를 사용 하는 프로그램의 동일한 빌드를 사용 하면 형식 정보 포함. 그러나 형식 포함 된 완전히 관리 되는 솔루션을 사용할 수 있습니다.  
  
 다음과 같은 특징이 있는 어셈블리에서 형식 정보를 포함할 수 있습니다.  
  
-   어셈블리는 하나 이상의 공용 인터페이스를 제공합니다.  
  
-   포함 된 인터페이스 주석을 지정 하 여 한 `ComImport` 특성 및 `Guid` 특성 (및 고유 GUID)입니다.  
  
-   어셈블리 주석이 추가 되는 `ImportedFromTypeLib` 특성 또는 `PrimaryInteropAssembly` 특성 및 해당 어셈블리 수준 `Guid` 특성입니다. (기본적으로 Visual Basic 프로젝트 템플릿에 포함 어셈블리 수준의 `Guid` 특성입니다.)  
  
 포함할 수 있는 공용 인터페이스를 지정한 후에 이러한 인터페이스를 구현 하는 런타임 클래스를 만들 수 있습니다. 클라이언트 프로그램 수는 공용 인터페이스 및 설정을 포함 하는 어셈블리를 참조 하 여 디자인 타임에 이러한 인터페이스에 대 한 형식 정보를 포함 한 다음는 `Embed Interop Types` 속성에 대 한 참조의 `True`합니다. 이 해당 명령줄 컴파일러를 사용 하 고 사용 하 여 어셈블리를 참조 하는 `/link` 컴파일러 옵션입니다. 클라이언트 프로그램에서 이러한 인터페이스로 형식화 된 런타임 개체의 인스턴스를 로드할 수 있습니다. 강력한 이름의 런타임 어셈블리의 새 버전을 만들면 클라이언트 프로그램 없는 업데이트 된 런타임 어셈블리로 컴파일해야 합니다. 대신, 클라이언트 프로그램에서 사용 하는 어떤 버전의 런타임 어셈블리를 사용할 수 있는 공용 인터페이스에 포함된 된 형식 정보를 사용 하 여 계속 합니다.  
  
 COM interop 어셈블리에서 형식 정보를 포함 하도록 지 원하는 형식 포함의 기본 기능은 이기 때문에 완전히 관리 되는 솔루션에서 형식 정보를 포함 하는 경우 다음과 같은 제한 사항이 적용 됩니다.  
  
-   COM interop 관련 특성만 포함 됩니다. 다른 특성은 무시 됩니다.  
  
-   제네릭 매개 변수를 사용 하는 형식 및 제네릭 매개 변수의 형식이 포함된 된 형식, 해당 형식의 어셈블리 경계를 넘어 사용할 수 있습니다. 어셈블리 경계를 넘는 경우의 예로 다른 어셈블리에서 메서드 호출 또는 다른 어셈블리에 정의 된 형식에서 파생 되는 형식입니다.  
  
-   상수는 포함 되지 않습니다.  
  
-   <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>클래스 키로 포함된 된 형식을 지원 하지 않습니다.</xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> 사용자 고유의 사전 형식 키로 포함된 된 형식을 지원 하기 위해 구현할 수 있습니다.  
  
 이 연습에서는 다음을 수행 합니다.  
  
-   포함할 수 있는 형식 정보를 포함 하는 공용 인터페이스에 강력한 이름의 어셈블리를 만듭니다.  
  
-   해당 공용 인터페이스를 구현 하는 런타임 강력한 이름의 어셈블리를 만듭니다.  
  
-   런타임 어셈블리에서 클래스의 인스턴스를 만들고 공용 인터페이스에서 형식 정보를 포함 하는 클라이언트 프로그램을 만듭니다.  
  
-   수정 하 고 런타임 어셈블리를 다시 빌드하십시오.  
  
-   클라이언트 프로그램을 다시 컴파일할 필요 없이 런타임 어셈블리의 새 버전은 사용 하는지 확인 하기 위해 클라이언트 프로그램을 실행 합니다.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-an-interface"></a>인터페이스 만들기  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a>형식 동등성 인터페이스 프로젝트를 만들려면  
  
1.  Visual Studio에서에 **파일** 메뉴에서 **새로** 클릭 하 고 **프로젝트**합니다.  
  
2.  **새 프로젝트** 대화 상자는 **프로젝트 형식** 창에서 다음 사항을 확인 **Windows** 을 선택 합니다. 선택 **클래스 라이브러리** 에 **템플릿** 창입니다. 에 **이름** 상자에 입력 합니다 `TypeEquivalenceInterface`를 클릭 하 고 **확인**합니다. 새 프로젝트가 만들어집니다.  
  
3.  **솔루션 탐색기**Class1.vb 파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **이름 바꾸기**합니다. 파일을 이름 `ISampleInterface.vb` ENTER 키를 누릅니다. 클래스 이름도 바꿉니다 파일의 이름을 바꾸면 `ISampleInterface`합니다. 이 클래스는 클래스에 대 한 공용 인터페이스를 나타냅니다.  
  
4.  TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다. 클릭 하 고 **컴파일** 탭 합니다. 와 같은 개발 컴퓨터에 올바른 위치에 출력 경로 설정 `C:\TypeEquivalenceSample`합니다. 이 위치는이 연습에서 나중에도 사용 됩니다.  
  
5.  프로젝트 속성을 계속 편집 하는 동안 클릭는 **서명** 탭 합니다. 선택 된 **어셈블리에 서명** 옵션입니다. 에 **강력한 이름 키 파일 선택** 목록에서 클릭 ** <New...> **.</New...> 에 **키 파일 이름** 상자에 입력 합니다 `key.snk`합니다. 지우기는 **암호로 내 키 파일 보호** 확인란입니다. **확인**을 클릭합니다.  
  
6.  ISampleInterface.vb 파일을 엽니다. ISampleInterface 인터페이스를 만드는 ISampleInterface 클래스 파일에 다음 코드를 추가 합니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
7.  에 **도구** 메뉴를 클릭 하 여 **Guid 만들기**합니다. 에 **GUID 만들기** 대화 상자를 클릭 **레지스트리 형식** 클릭 하 고 **복사**합니다. **끝내기**를 클릭합니다.  
  
8.  에 `Guid` 특성, 샘플 GUID를 삭제 하 고,에서 복사한 GUID에 붙여는 **GUID 만들기** 대화 상자입니다. 복사 된 GUID에서 중괄호 ({})를 제거 합니다.  
  
9. 에 **프로젝트** 메뉴를 클릭 하 여 **모든 파일 표시**합니다.  
  
10. **솔루션 탐색기**를 확장 하 고는 **My Project** 폴더입니다. AssemblyInfo.vb를 두 번 클릭 합니다. 파일에 다음 특성을 추가 합니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
     파일을 저장합니다.  
  
11. 프로젝트를 저장합니다.  
  
12. TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **빌드**합니다. 클래스 라이브러리.dll 파일 컴파일되고 지정한 빌드 출력 경로 (예를 들어 C:\TypeEquivalenceSample)에 저장 됩니다.  
  
## <a name="creating-a-runtime-class"></a>런타임 클래스 만들기  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a>형식 동등성 런타임 프로젝트를 만들려면  
  
1.  Visual Studio에서에 **파일** 메뉴에서 **새로** 클릭 하 고 **프로젝트**합니다.  
  
2.  **새 프로젝트** 대화 상자는 **프로젝트 형식** 창에서 다음 사항을 확인 **Windows** 을 선택 합니다. 선택 **클래스 라이브러리** 에 **템플릿** 창입니다. 에 **이름** 상자에 입력 합니다 `TypeEquivalenceRuntime`를 클릭 하 고 **확인**합니다. 새 프로젝트가 만들어집니다.  
  
3.  **솔루션 탐색기**Class1.vb 파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **이름 바꾸기**합니다. 파일을 이름 `SampleClass.vb` ENTER 키를 누릅니다. 클래스의 이름을 파일의 이름을 바꾸면 `SampleClass`합니다. 이 클래스가 구현 하는 `ISampleInterface` 인터페이스입니다.  
  
4.  TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다. 클릭 하 고 **컴파일** 탭 합니다. 예를 들어 TypeEquivalenceInterface 프로젝트에서 사용한 동일한 위치에 출력 경로 설정 `C:\TypeEquivalenceSample`합니다.  
  
5.  프로젝트 속성을 계속 편집 하는 동안 클릭는 **서명** 탭 합니다. 선택 된 **어셈블리에 서명** 옵션입니다. 에 **강력한 이름 키 파일 선택** 목록에서 클릭 ** <New...> **.</New...> 에 **키 파일 이름** 상자에 입력 합니다 `key.snk`합니다. 지우기는 **암호로 내 키 파일 보호** 확인란입니다. **확인**을 클릭합니다.  
  
6.  TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **참조 추가**합니다. 클릭 하 고 **찾아보기** 탭 및 출력 경로 폴더를 찾습니다. TypeEquivalenceInterface.dll 파일을 선택 하 고 클릭 **확인**합니다.  
  
7.  에 **프로젝트** 메뉴를 클릭 하 여 **모든 파일 표시**합니다.  
  
8.  **솔루션 탐색기**를 확장 하 고는 **참조** 폴더입니다. TypeEquivalenceInterface 파일에 대 한 참조를 선택 합니다. TypeEquivalenceInterface 참조에 대 한 속성 창에서 설정 된 **특정 버전** 속성을 **False**합니다.  
  
9. SampleClass 클래스를 만드는 SampleClass 클래스 파일에 다음 코드를 추가 합니다.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
10. 프로젝트를 저장합니다.  
  
11. TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **빌드**합니다. 클래스 라이브러리.dll 파일 컴파일되고 지정한 빌드 출력 경로 (예를 들어 C:\TypeEquivalenceSample)에 저장 됩니다.  
  
## <a name="creating-a-client-project"></a>클라이언트 프로젝트 만들기  
  
#### <a name="to-create-the-type-equivalence-client-project"></a>형식 동등성 클라이언트 프로젝트를 만들려면  
  
1.  Visual Studio에서에 **파일** 메뉴에서 **새로** 클릭 하 고 **프로젝트**합니다.  
  
2.  **새 프로젝트** 대화 상자는 **프로젝트 형식** 창에서 다음 사항을 확인 **Windows** 을 선택 합니다. 선택 **콘솔 응용 프로그램** 에 **템플릿** 창입니다. 에 **이름** 상자에 입력 합니다 `TypeEquivalenceClient`를 클릭 하 고 **확인**합니다. 새 프로젝트가 만들어집니다.  
  
3.  TypeEquivalenceClient 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다. 클릭 하 고 **컴파일** 탭 합니다. 예를 들어 TypeEquivalenceInterface 프로젝트에서 사용한 동일한 위치에 출력 경로 설정 `C:\TypeEquivalenceSample`합니다.  
  
4.  TypeEquivalenceClient 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **참조 추가**합니다. 클릭 하 고 **찾아보기** 탭 및 출력 경로 폴더를 찾습니다. TypeEquivalenceInterface.dll 파일 (TypeEquivalenceRuntime.dll 하지)를 선택 하 고 클릭 **확인**합니다.  
  
5.  에 **프로젝트** 메뉴를 클릭 하 여 **모든 파일 표시**합니다.  
  
6.  **솔루션 탐색기**를 확장 하 고는 **참조** 폴더입니다. TypeEquivalenceInterface 파일에 대 한 참조를 선택 합니다. TypeEquivalenceInterface 참조에 대 한 속성 창에서 설정 된 **Interop 형식 포함** 속성을 **True**합니다.  
  
7.  클라이언트 프로그램을 만드는 Module1.vb 파일에 다음 코드를 추가 합니다.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
8.  빌드하고 프로그램을 실행 하려면 CTRL + f&5;를 누릅니다.  
  
## <a name="modifying-the-interface"></a>인터페이스 수정  
  
#### <a name="to-modify-the-interface"></a>인터페이스를 수정 하려면  
  
1.  Visual Studio에서에 **파일** 메뉴에서 **열려**를 클릭 하 고 **프로젝트/솔루션**합니다.  
  
2.  에 **프로젝트 열기** 대화 상자 TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 **속성**합니다. **응용 프로그램** 탭을 클릭합니다. 클릭 하 고 **어셈블리 정보** 단추입니다. 변경 된 **어셈블리 버전** 및 **파일 버전** 값을 `2.0.0.0`합니다.  
  
3.  ISampleInterface.vb 파일을 엽니다. ISampleInterface 인터페이스에 다음 코드 줄을 추가 합니다.  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
     파일을 저장합니다.  
  
4.  프로젝트를 저장합니다.  
  
5.  TypeEquivalenceInterface 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **빌드**합니다. 클래스 라이브러리.dll 파일의 새 버전 컴파일되고 지정한 빌드 출력 경로 (예를 들어 C:\TypeEquivalenceSample)에 저장 됩니다.  
  
## <a name="modifying-the-runtime-class"></a>런타임 클래스 수정  
  
#### <a name="to-modify-the-runtime-class"></a>런타임 클래스를 수정 하려면  
  
1.  Visual Studio에서에 **파일** 메뉴에서 **열려**를 클릭 하 고 **프로젝트/솔루션**합니다.  
  
2.  에 **프로젝트 열기** 대화 상자 TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다. **응용 프로그램** 탭을 클릭합니다. 클릭 하 고 **어셈블리 정보** 단추입니다. 변경 된 **어셈블리 버전** 및 **파일 버전** 값을 `2.0.0.0`합니다.  
  
3.  SampleClass.vbfile를 엽니다. SampleClass 클래스에 다음 코드 줄을 추가 합니다.  
  
```vb  
Public Function GetDate() As DateTime Implements ISampleInterface.GetDate  
    Return Now  
End Function  
```  
  
     Save the file.  
  
4.  프로젝트를 저장합니다.  
  
5.  TypeEquivalenceRuntime 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **빌드**합니다. 클래스 라이브러리.dll 파일의 업데이트 된 버전 컴파일되고 이전에 지정한 빌드 출력 경로 (예를 들어 C:\TypeEquivalenceSample)에 저장 됩니다.  
  
6.  파일 탐색기에서 출력 경로 폴더 (예를 들어 C:\TypeEquivalenceSample)를 엽니다. 프로그램을 실행 하려면 TypeEquivalenceClient.exe를 두 번 클릭 합니다. 프로그램은 다시 컴파일되지 않았이 필요 없이 TypeEquivalenceRuntime 어셈블리의 새 버전을 반영 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)   
 [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)   
 [어셈블리를 사용한 프로그래밍](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)   
 [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)

