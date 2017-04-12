---
title: "방법: 리플렉션 (LINQ) (Visual Basic) 사용 하 여 어셈블리의 메타 데이터 쿼리 | Microsoft 문서"
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
ms.assetid: 53caa336-ab83-4181-b0f6-5c87c5f9e4ee
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7c1bc26d7b23135dd45ad58ea0bd2510b7157448
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-query-an-assembly39s-metadata-with-reflection-linq-visual-basic"></a>방법: 리플렉션 (LINQ) (Visual Basic) 사용 하 여 어셈블리의 메타 데이터 쿼리
다음 예제에서는 지정 된 검색 조건과 일치 하는 방법에 대 한 특정 메타 데이터를 검색할 리플렉션을 사용 하 여 LINQ에 사용할 수는 방법을 보여줍니다. 이 경우에 쿼리는 배열과 같은 열거 가능한 형식을 반환 하는 어셈블리의 모든 메서드의 이름을 검색 합니다.  
  
## <a name="example"></a>예제  
  
```vb  
Imports System.Reflection  
Imports System.IO  
Imports System.Linq  
Module Module1  
  
    Sub Main()  
        Dim asmbly As Assembly =   
            Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089")  
  
        Dim pubTypesQuery = From type In asmbly.GetTypes()   
                            Where type.IsPublic   
                            From method In type.GetMethods()   
                            Where method.ReturnType.IsArray = True   
                            Let name = method.ToString()   
                            Let typeName = type.ToString()   
                            Group name By typeName Into methodNames = Group  
  
        Console.WriteLine("Getting ready to iterate")  
        For Each item In pubTypesQuery  
            Console.WriteLine(item.methodNames)  
  
            For Each type In item.methodNames  
                Console.WriteLine(" " & type)  
            Next  
        Next  
        Console.ReadKey()  
    End Sub  
  
End Module  
```  
  
 이 예제에서는 사용 된 <xref:System.Reflection.Assembly.GetTypes%2A>메서드를 지정된 된 어셈블리에서 형식의 배열을 반환 합니다.</xref:System.Reflection.Assembly.GetTypes%2A> [Where 절](../../../../visual-basic/language-reference/queries/where-clause.md) public 형식만 반환 되도록 필터 적용 됩니다. 각 공용 형식에 대해 하위 쿼리를 사용 하 여 생성 됩니다는 <xref:System.Reflection.MethodInfo>배열에서 반환 되는 <xref:System.Type.GetMethods%2A>호출.</xref:System.Type.GetMethods%2A> </xref:System.Reflection.MethodInfo> 이러한 결과는 해당 반환 형식이 <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> 를 구현 하는 형식을 그렇지 배열 하는 방법에만 반환 하는 필터링 됩니다. 마지막으로, 이러한 결과 형식 이름을 키로 사용 하 여 그룹화 됩니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 .NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` 는 System.Linq 네임 스페이스에 대 한 정보입니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
