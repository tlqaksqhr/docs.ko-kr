---
title: '방법: 네임스페이스 접두사 제어(Visual Basic)(LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: f60f90ef6742dfd725f51ff7e760436117346e85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641682"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a>방법: 네임스페이스 접두사 제어(Visual Basic)(LINQ to XML)
이 항목에서는 네임스페이스 접두사를 제어하는 방법에 대해 설명합니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 이 예제에서는 두 네임스페이스를 선언한 다음 갖도록 지정는 `http://www.adventure-works.com` 네임 스페이스가 `aw`, 있고는 `www.fourthcoffee.com` 네임 스페이스의 접두사에 `fc`합니다.  
  
### <a name="code"></a>코드  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
### <a name="comments"></a>설명  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
