---
title: "Visual Basic에서 기본 네임 스페이스 범위 | Microsoft 문서"
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
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c0152250cf7cfb4b6cadbcaab60eaad8ec2fb5ee
ms.lasthandoff: 03/13/2017


---
# <a name="scope-of-default-namespaces-in-visual-basic"></a>Visual Basic에서 기본 네임 스페이스의 범위
XML 트리에 나타나는 기본 네임스페이스는 쿼리에 범위에 포함되지 않습니다. 있으면 기본 네임 스페이스에 있는 XML을 선언는 <xref:System.Xml.Linq.XNamespace>변수는 쿼리에서 사용할 정규화 된 이름을 확인 하 고 로컬 이름과 결합.</xref:System.Xml.Linq.XNamespace>  
  
 XML 트리를 쿼리할 때 가장 일반적인 문제 중 하나는 XML 트리에 기본 네임스페이스가 있으면 개발자가 경우에 따라 XML이 네임스페이스에 없는 것처럼 쿼리를 작성하는 것입니다.  
  
 이 항목의 첫 번째 예제 집합에서는 기본 네임스페이스의 XML이 로드되지만 적절하지 않게 쿼리되는 일반적인 방법을 보여 줍니다.  
  
 두 번째 예제 집합에서는 네임스페이스의 XML을 쿼리할 수 있도록 필요한 수정을 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 네임스페이스에 XML을 만들고 빈 결과 집합을 반환하는 쿼리를 만드는 방법을 보여 줍니다.  
  
### <a name="code"></a>코드  
  
```vb  
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
  
### <a name="comments"></a>설명  
 이 예제의 결과는 다음과 같습니다.  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 네임스페이스에 XML을 만들고 제대로 코딩된 쿼리를 만드는 방법을 보여 줍니다.  
  
 위의 잘못 코딩 된 예제와 달리 Visual Basic을 사용 하는 경우의 올바른 방법은 선언 하 고 전역 기본 네임 스페이스를 초기화 합니다. 이렇게 하면 기본 네임스페이스에 모든 XML 속성이 배치됩니다. 예제가 제대로 작동하도록 하기 위해 다른 수정은 필요하지 않습니다.  
  
### <a name="code"></a>코드  
  
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
            Console.WriteLine(el.Value)  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>설명  
 이 예제의 결과는 다음과 같습니다.  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
