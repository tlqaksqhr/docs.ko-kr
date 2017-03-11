---
title: "Walkthrough: Implementing IEnumerable(Of T) in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "control flow [Visual Basic]"
  - "enumerable interfaces"
  - "loop structures, optimizing performance"
  - "control flow"
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Walkthrough: Implementing IEnumerable(Of T) in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:System.Collections.Generic.IEnumerable%601> 인터페이스는 한 번에 한 항목씩 값 시퀀스를 반환할 수 있는 클래스에서 구현됩니다.  한 번에 한 항목씩 데이터를 반환하면 전체 데이터 집합을 메모리에 로드하지 않고도 작업을 처리할 수 있다는 장점이 있습니다.  전체 데이터 중 단일 항목을 로드할 수 있는 메모리 공간만 사용하면 됩니다.  `IEnumerable(T)` 인터페이스를 구현하는 클래스는 `For Each` 루프 또는 LINQ 쿼리와 함께 사용할 수 있습니다.  
  
 예를 들어, 대용량 텍스트 파일을 읽고 파일에서 특정 검색 조건과 일치하는 각 줄을 반환해야 하는 응용 프로그램이 있다고 가정합니다.  이 응용 프로그램에서는 LINQ 쿼리를 사용하여 파일에서 지정된 조건과 일치하는 줄을 반환합니다.  LINQ 쿼리를 사용하여 파일의 내용을 쿼리하기 위해 응용 프로그램에서 파일의 내용을 배열이나 컬렉션에 로드할 수 있습니다.  하지만 전체 파일을 배열이나 컬렉션에 로드하게 되면 필요한 용량보다 훨씬 많은 메모리를 사용하게 됩니다.  LINQ 쿼리는 그 대신 열거 가능한 클래스를 사용하여 파일 내용을 쿼리한 후 검색 조건과 일치하는 값만 반환할 수 있습니다.  일치하는 소수의 값만 반환하는 쿼리를 사용하면 메모리 사용량이 크게 줄어듭니다.  
  
 소스 데이터를 열거 가능한 데이터로 노출하는 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현하는 클래스를 만들 수 있습니다.  `IEnumerable(T)` 인터페이스를 구현하는 클래스를 사용하려면 소스 데이터를 반복하기 위해 <xref:System.Collections.Generic.IEnumerator%601> 인터페이스를 구현하는 다른 클래스가 필요합니다.  이러한 두 클래스를 사용하면 데이터 항목을 순차적으로 특정 형식으로 반환할 수 있습니다.  
  
 이 연습에서는 `IEnumerable(Of String)` 인터페이스를 구현하는 클래스와 `IEnumerator(Of String)` 인터페이스를 구현하는 클래스를 만들어서 한 번에 한 줄씩 텍스트 파일을 읽습니다.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
## 열거 가능한 클래스 만들기  
  
||  
|-|  
|열거 가능한 클래스 프로젝트를 만들려면|  
|1.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.<br />2.  **새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.  **템플릿** 창에서 **클래스 라이브러리**를 선택합니다.  **이름** 상자에 `StreamReaderEnumerable`을 입력하고 **확인**을 클릭합니다.  새 프로젝트가 표시됩니다.<br />3.  **솔루션 탐색기**에서 Class1.vb 파일을 마우스 오른쪽 단추로 클릭한 다음 **이름 바꾸기**를 클릭합니다.  파일의 이름을 `StreamReaderEnumerable.vb`로 바꾸고 Enter 키를 누릅니다.  파일의 이름을 바꾸면 클래스의 이름도 `StreamReaderEnumerable`로 바뀝니다.  이 클래스는 `IEnumerable(Of String)` 인터페이스를 구현합니다.<br />4.  StreamReaderEnumerable 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 항목**을 클릭합니다.  **클래스** 템플릿을 선택합니다.  **이름** 상자에 `StreamReaderEnumerator.vb`를 입력하고 **확인**을 클릭합니다.|  
  
 이 프로젝트의 첫 번째 클래스는 열거 가능한 클래스로서 `IEnumerable(Of String)` 인터페이스를 구현합니다.  이 제네릭 인터페이스는 <xref:System.Collections.IEnumerable> 인터페이스를 구현하고 이 클래스의 사용자가 `String` 형식의 값에 액세스할 수 있도록 해 줍니다.  
  
||  
|-|  
|IEnumerable을 구현하는 코드를 추가하려면|  
|1.  StreamReaderEnumerable.vb 파일을 엽니다.<br />2.  `Public Class StreamReaderEnumerable` 다음 줄에 다음과 같이 입력하고 Enter 키를 누릅니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#1)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 자동으로 이 클래스를 `IEnumerable(Of String)` 인터페이스에 필요한 멤버로 채웁니다.<br />3.  이 열거 가능한 클래스는 텍스트 파일을 한 번에 한 줄씩 읽습니다.  파일 경로를 입력 매개 변수로 받는 public 생성자를 노출하는 다음 코드를 클래스에 추가합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#2)]<br />4.  `IEnumerable(Of String)` 인터페이스의 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 메서드 구현에서 `StreamReaderEnumerator` 클래스의 새 인스턴스를 반환합니다.  `IEnumerable(Of String)` 인터페이스의 멤버만 노출해야 하므로 `IEnumerable` 인터페이스의 `GetEnumerator` 메서드 구현을 `Private`로 만들 수 있습니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 `GetEnumerator` 메서드에 대해 생성한 코드를 다음 코드로 바꿉니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#3)]|  
  
||  
|-|  
|IEnumerator를 구현하는 코드를 추가하려면|  
|1.  StreamReaderEnumerator.vb 파일을 엽니다.<br />2.  `Public Class StreamReaderEnumerator` 다음 줄에 다음과 같이 입력하고 Enter 키를 누릅니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#4)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 자동으로 이 클래스를 `IEnumerator(Of String)` 인터페이스에 필요한 멤버로 채웁니다.<br />3.  열거자 클래스는 텍스트 파일을 열고 파일 I\/O를 수행하여 파일의 줄을 읽습니다.  파일 경로를 입력 매개 변수로 받는 public 생성자를 노출한 후 텍스트 파일을 열어서 읽는 다음 코드를 클래스에 추가합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#5)]<br />4.  `IEnumerator(Of String)` 및 `IEnumerator` 인터페이스에 대한 `Current` 속성은 텍스트 파일의 현재 항목을 `String`으로 반환합니다.  `IEnumerator(Of String)` 인터페이스의 멤버만 노출해야 하므로 `IEnumerator` 인터페이스의 `Current` 속성 구현을 `Private`로 만들 수 있습니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 `Current` 속성에 대해 생성한 코드를 다음 코드로 바꿉니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#6)]<br />5.  `IEnumerator` 인터페이스의 `MoveNext` 메서드는 텍스트 파일의 다음 항목으로 이동하여 `Current` 속성에서 반환된 값을 업데이트합니다.  읽을 항목이 더 이상 없으면 `MoveNext` 메서드에서 `False`를 반환하고, 그렇지 않으면 `MoveNext` 메서드에서 `True`를 반환합니다.  `MoveNext` 메서드에 다음 코드를 추가합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#7)]<br />6.  `IEnumerator` 인터페이스의 `Reset` 메서드가 반복기에게 텍스트 파일의 시작을 가리키도록 지시한 후 현재 항목 값을 지웁니다.  `Reset` 메서드에 다음 코드를 추가합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#8)]<br />7.  `IEnumerator` 인터페이스의 `Dispose` 메서드는 반복기가 소멸되기 전에 관리되지 않는 모든 리소스가 해제되도록 보장합니다.  `StreamReader` 개체에서 사용되는 파일 핸들은 관리되지 않은 리소스이므로 반복기 인스턴스가 소멸되기 전에 닫혀야 합니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 `Dispose` 메서드에 대해 생성한 코드를 다음 코드로 바꿉니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#9)]|  
  
## 샘플 반복기 사용  
 코드에서 열거 가능한 클래스를 `For Next` 루프 또는 LINQ 쿼리와 같이 `IEnumerable`을 구현하는 개체가 필요한 제어 구조와 함께 사용할 수 있습니다.  다음 예제에서는 LINQ 쿼리의 `StreamReaderEnumerable`을 보여 줍니다.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/Module1.vb#10)]  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)