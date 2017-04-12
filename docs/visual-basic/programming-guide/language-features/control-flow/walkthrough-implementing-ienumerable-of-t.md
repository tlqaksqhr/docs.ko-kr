---
title: "Visual Basic에서 ienumerable 인터페이스를 구현 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures, optimizing performance
- control flow
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 68c37c46cbceb1056d50972cdc58ddb7c7577447
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>연습: Visual Basic에서 IEnumerable(Of T) 구현
<xref:System.Collections.Generic.IEnumerable%601>인터페이스는 한 번에 한 항목씩 값의 시퀀스를 반환할 수 있는 클래스에 의해 구현 됩니다.</xref:System.Collections.Generic.IEnumerable%601> 데이터를 한 번에 하나의 항목을 작동 하는 메모리에 완전 한 데이터 집합을 로드할 필요가 없습니다 반환 활용 합니다. 충분 한 메모리를 사용 하 여 데이터에서 단일 항목을 로드 해야 합니다. 구현 하는 클래스는 `IEnumerable(T)` 인터페이스를 함께 사용할 수 `For Each` 루프 또는 LINQ 쿼리 합니다.  
  
 예를 들어 큰 텍스트 파일을 읽고 특정 검색 조건과 일치 하는 파일에서 각 줄을 반환 해야 하는 응용 프로그램을 고려해 야 합니다. 응용 프로그램 LINQ 쿼리를 사용 하 여 지정된 된 조건과 일치 하는 파일의 줄을 반환 합니다. LINQ 쿼리를 사용 하 여 파일의 내용을 퀴리, 응용 프로그램 배열 또는 컬렉션에 파일의 내용을 로드할 수 있습니다. 그러나 배열 또는 컬렉션에 전체 파일을 로드 필요한 것 보다 훨씬 더 많은 메모리를 사용 합니다. LINQ 쿼리 대신 검색 조건과 일치 하는 값만 반환 하는 열거 가능한 클래스를 사용 하 여 파일 콘텐츠를 쿼리할 수 있습니다. 일부만 반환 하는 쿼리 훨씬 적은 메모리를 사용할 일치 하는 값입니다.  
  
 구현 하는 클래스를 만들 수는 <xref:System.Collections.Generic.IEnumerable%601>열거 가능한 데이터 원본 데이터를 노출 하는 인터페이스입니다.</xref:System.Collections.Generic.IEnumerable%601> 구현 하는 클래스는 `IEnumerable(T)` 인터페이스를 구현 하는 다른 클래스에서는 <xref:System.Collections.Generic.IEnumerator%601>원본 데이터를 반복 하는 인터페이스입니다.</xref:System.Collections.Generic.IEnumerator%601> 이러한 두 클래스를 사용 하 여 항목의 데이터를 특정 형식으로 순차적으로 반환할 수 있습니다.  
  
 이 연습에서는 구현 하는 클래스를 만듭니다는 `IEnumerable(Of String)` 인터페이스를 구현 하는 클래스는 `IEnumerator(Of String)` 인터페이스를 한 줄씩 텍스트 파일을 한 번에 읽을 수 있습니다.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-the-enumerable-class"></a>열거 가능한 클래스 만들기  
  
|Enumerable 클래스 프로젝트를 만들려면|  
|---|  
|1.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에 **파일** 메뉴에서 **새로** 클릭 하 고 **프로젝트**합니다.<br />2.  **새 프로젝트** 대화 상자는 **프로젝트 형식** 창에서 다음 사항을 확인 **Windows** 을 선택 합니다. 선택 **클래스 라이브러리** 에 **템플릿** 창입니다. 에 **이름** 상자에 입력 합니다 `StreamReaderEnumerable`를 클릭 하 고 **확인**합니다. 새 프로젝트가 표시 됩니다.<br />3.  **솔루션 탐색기**Class1.vb 파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **이름 바꾸기**합니다. 파일을 이름 `StreamReaderEnumerable.vb` ENTER 키를 누릅니다. 클래스 이름도 바꿉니다 파일의 이름을 바꾸면 `StreamReaderEnumerable`합니다. 이 클래스가 구현 하는 `IEnumerable(Of String)` 인터페이스입니다.<br />4.  StreamReaderEnumerable 프로젝트를 마우스 오른쪽 **추가**를 클릭 하 고 **새 항목**합니다. 선택 된 **클래스** 템플릿. 에 **이름** 상자에 입력 합니다 `StreamReaderEnumerator.vb` 클릭 **확인**합니다.|  
  
 이 프로젝트의 첫 번째 클래스 enumerable 클래스 이며 구현에서 `IEnumerable(Of String)` 인터페이스입니다. 이 제네릭 인터페이스를 구현 하는 <xref:System.Collections.IEnumerable>인터페이스와이 클래스의 소비자로 형식화 된 값에 액세스할 수 있도록 보장 `String`.</xref:System.Collections.IEnumerable>  
  
|IEnumerable을 구현 하는 코드를 추가 하려면|  
|---|  
|1.  StreamReaderEnumerable.vb 파일을 엽니다.<br />2.  다음 줄에 `Public Class StreamReaderEnumerable`를 입력 한 다음 ENTER 키를 누릅니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough #&1;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에 필요한 멤버를 사용 하 여 클래스를 자동으로 채웁니다는 `IEnumerable(Of String)` 인터페이스입니다.<br />3.  이 enumerable 클래스는 한 번에는 한 줄씩 텍스트 파일에서에서 줄을 읽습니다. 파일 경로 입력된 매개 변수로 받아들이는 public 생성자를 노출 하는 클래스에 다음 코드를 추가 합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough #&2;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]<br />4.  구현 된 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>의 메서드는 `IEnumerable(Of String)` 인터페이스의 새 인스턴스를 반환 합니다는 `StreamReaderEnumerator` 클래스</xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 구현에서 `GetEnumerator` 의 메서드는 `IEnumerable` 인터페이스를 만들 수 있습니다 `Private`의 멤버만 노출 해야 하기 때문에는 `IEnumerable(Of String)` 인터페이스. 코드는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 에 대해 생성 되는 `GetEnumerator` 메서드를 다음 코드로 합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough #&3;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]|  
  
|IEnumerator를 구현 하는 코드를 추가 하려면|  
|---|  
|1.  StreamReaderEnumerator.vb 파일을 엽니다.<br />2.  다음 줄에 `Public Class StreamReaderEnumerator`를 입력 한 다음 ENTER 키를 누릅니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough #&4;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에 필요한 멤버를 사용 하 여 클래스를 자동으로 채웁니다는 `IEnumerator(Of String)` 인터페이스입니다.<br />3.  열거자 클래스 텍스트 파일이 열리고 파일 I/O 파일에서 줄 읽기를 수행 합니다. 다음 코드를 파일 경로 입력된 매개 변수로 받아들이는 public 생성자를 노출 하 고 읽기에 대 한 텍스트 파일을 열고 클래스에 추가 합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough #&5;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]<br />4.  `Current` 둘 다에 대 한 속성의 `IEnumerator(Of String)` 및 `IEnumerator` 으로 텍스트 파일에서 현재 항목을 반환 하는 인터페이스는 `String`합니다. 구현은 `Current` 의 속성은 `IEnumerator` 인터페이스를 만들 수 있습니다 `Private`의 멤버만 노출 해야 하기 때문에는 `IEnumerator(Of String)` 인터페이스입니다. 코드는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 에 대해 생성 되는 `Current` 다음 코드를 사용 하 여 속성.<br />     [!code-vb[VbVbalrIteratorWalkthrough #&6;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]<br />5.  `MoveNext` 의 메서드는 `IEnumerator` 인터페이스는 텍스트 파일에서 다음 항목으로 이동 하 고에서 반환 되는 값을 업데이트 하는 `Current` 속성입니다. 읽기, 항목이 더 이상 없으면는 `MoveNext` 메서드 반환 `False`고, 그렇지 않으면는 `MoveNext` 메서드 반환 `True`합니다. `MoveNext` 메서드에 다음 코드를 추가합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough #&7;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]<br />6.  `Reset` 의 메서드는 `IEnumerator` 인터페이스는 텍스트 파일의 시작 부분을 가리키는 반복기를 지시 하 고 현재 항목 값을 지웁니다. `Reset` 메서드에 다음 코드를 추가합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough #&8;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]<br />7.  `Dispose` 의 메서드는 `IEnumerator` 인터페이스 보장 하는 반복기를 삭제 하기 전에 관리 되지 않는 리소스를 모두 해제 됩니다. 사용 되는 파일 핸들은 `StreamReader` 개체는 관리 되지 않는 리소스 및 반복기 인스턴스가 소멸 되기 전에 닫아야 합니다. 코드는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 에 대해 생성 된는 `Dispose` 메서드를 다음 코드로 바꿉니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough #&9;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)]|  
  
## <a name="using-the-sample-iterator"></a>샘플 반복기 사용  
 열거 가능한 클래스를 사용 하 여 구현 하는 개체를 필요로 하는 제어 구조와 함께 코드에서 `IEnumerable`와 같은 `For Next` 루프 또는 LINQ 쿼리입니다. 다음 예제는 `StreamReaderEnumerable` LINQ 쿼리에서 합니다.  
  
 [!code-vb[VbVbalrIteratorWalkthrough #&10;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [제어 흐름](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)

