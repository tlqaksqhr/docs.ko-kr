---
title: "방법: LINQ to XML 예제 빌드(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e5d18fa1-2704-48fe-a44b-1564f97c9e9c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a8ec8a4b5ad976bd09364eab51ecb4981e83b5d0
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-build-linq-to-xml-examples-c"></a>방법: LINQ to XML 예제 빌드(C#)
이 설명서의 다양한 코드 조각과 예제에서는 여러 가지 네임스페이스의 클래스와 형식을 사용합니다. C# 코드를 컴파일하는 경우 적절한 `using` 지시문을 제공해야 하고,  
  
## <a name="example"></a>예제  
 다음 코드에는 C# 예제에서 빌드하고 실행해야 하는 `using` 지시문이 포함되어 있습니다. 모든 `using` 지시문이 모든 예제에 필요한 것은 아닙니다.  
  
```csharp  
using System;  
using System.Diagnostics;  
using System.Collections;  
using System.Collections.Generic;  
using System.Collections.Specialized;  
using System.Text;  
using System.Linq;  
using System.Xml;  
using System.Xml.Linq;  
using System.Xml.Schema;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
using System.IO;  
using System.Threading;  
using System.Reflection;  
using System.IO.Packaging;  
```  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML 프로그래밍 개요(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
