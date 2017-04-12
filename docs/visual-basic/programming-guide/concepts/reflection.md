---
title: "리플렉션 (Visual Basic) | Microsoft 문서"
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
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3ae042933575849e105d7b681634a61319c1d6ee
ms.lasthandoff: 03/13/2017

---
# <a name="reflection-visual-basic"></a>리플렉션 (Visual Basic)
리플렉션은 개체를 제공 (형식의 <xref:System.Type>) 어셈블리, 모듈 및 형식을 설명 하는.</xref:System.Type> 리플렉션을 사용 하 여 동적으로 형식 인스턴스를 만들 형식을 기존 개체에 바인딩하거나, 기존 개체에서 형식을 가져오고 해당 메서드를 호출 또는 필드와 속성에 액세스할 수 있습니다. 특성 코드를 사용 하는 경우 리플렉션을 통해 액세스할 수 있습니다. 자세한 내용은 참조 [특성](https://msdn.microsoft.com/library/5x6cd29c)합니다.  
  
 다음은 정적 메서드를 사용 하 여 리플렉션의 간단한 예제 `GetType` 모든 형식에서 상속 되는 `Object` 기본 클래스는 변수의 형식을 가져옵니다.  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 출력이 됩니다.  
  
 `System.Int32`  
  
 다음 예제에서는 리플렉션을 사용 하 여 로드 된 어셈블리의 전체 이름을 얻을 수 있습니다.  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 출력이 됩니다.  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a>리플렉션 개요  
 리플렉션은 다음과 같은 상황에서 유용합니다.  
  
-   특성 프로그램의 메타 데이터에 액세스 해야 하는 경우. 자세한 내용은 참조 [검색 특성에 저장 된 정보](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)합니다.  
  
-   검사 하 고 어셈블리의 형식 인스턴스화입니다.  
  
-   런타임에 새 형식을 빌드해야 합니다. <xref:System.Reflection.Emit>.</xref:System.Reflection.Emit> 클래스를 사용 합니다.  
  
-   런타임에 바인딩을, 런타임에 작성 된 형식의 메서드에 액세스를 수행 합니다. 항목을 참조 하십시오 [형식 동적 로드 및 사용](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc)합니다.  
  
## <a name="related-sections"></a>관련 단원  
 추가 정보  
  
-   [리플렉션](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)  
  
-   [형식 정보 보기](http://msdn.microsoft.com/library/7e7303a9-4064-4738-b4e7-b75974ed70d2)  
  
-   [리플렉션 및 제네릭 형식](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)  
  
-   <xref:System.Reflection.Emit></xref:System.Reflection.Emit>  
  
-   [특성에 저장 된 정보 검색](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 프로그래밍 가이드](../../../visual-basic/programming-guide/index.md)   
 [공용 언어 런타임의 어셈블리](https://msdn.microsoft.com/library/k3677y81)
