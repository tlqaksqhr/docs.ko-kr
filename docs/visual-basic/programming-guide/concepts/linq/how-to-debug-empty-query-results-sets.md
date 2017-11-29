---
title: "방법: 빈 쿼리 결과 집합 (Visual Basic) 디버깅"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b242c90a-d2b8-4309-8a1e-e4e70736c727
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1c483153f8ff41c08cfaa0141fed056de7f5f680
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-debug-empty-query-results-sets-visual-basic"></a>방법: 빈 쿼리 결과 집합 (Visual Basic) 디버깅
XML 트리를 쿼리할 때 가장 일반적인 문제 중 하나는 XML 트리에 기본 네임스페이스가 있으면 개발자가 경우에 따라 XML이 네임스페이스에 없는 것처럼 쿼리를 작성하는 것입니다.  
  
 이 항목의 첫 번째 예제 집합에서는 기본 네임스페이스의 XML이 로드되고 적절하지 않게 쿼리되는 일반적인 방법을 보여 줍니다.  
  
 두 번째 예제 집합에서는 네임스페이스의 XML을 쿼리할 수 있도록 필요한 수정을 하는 방법을 보여 줍니다.  
  
 자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 네임스페이스에 XML을 만들고 빈 결과 집합을 반환하는 쿼리를 만드는 방법을 보여 줍니다.  
  
```vb  
Dim root As XElement = _  
    <Root xmlns='http://www.adventure-works.com'>  
        <Child>1</Child>  
        <Child>2</Child>  
        <Child>3</Child>  
        <AnotherChild>4</AnotherChild>  
        <AnotherChild>5</AnotherChild>  
        <AnotherChild>6</AnotherChild>  
    </Root>  
Dim c1 As IEnumerable(Of XElement) = _  
        From el In root.<Child> _  
        Select el  
Console.WriteLine("Result set follows:")  
For Each el As XElement In c1  
    Console.WriteLine(el.Value)  
Next  
Console.WriteLine("End of result set")  
```  
  
 이 예제의 결과는 다음과 같습니다.  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 네임스페이스에 XML을 만들고 제대로 코딩된 쿼리를 만드는 방법을 보여 줍니다.  
  
 솔루션은 선언 하 고 전역 기본 네임 스페이스를 초기화 합니다. 이렇게 하면 기본 네임스페이스에 모든 XML 속성이 배치됩니다. 예제가 제대로 작동하도록 하기 위해 다른 수정은 필요하지 않습니다.  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
 이 예제의 결과는 다음과 같습니다.  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a>참고 항목  
 [기본 쿼리 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
