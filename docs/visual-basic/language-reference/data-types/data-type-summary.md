---
title: "Data Type Summary (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Boolean data type, supported types in Visual Basic"
  - "storage, order of storage"
  - "data types [Visual Basic], Visual Basic"
  - "Single data type, supported types in Visual Basic"
  - "notation, scientific"
  - "memory requirements, data types"
  - "user-defined data types, Visual Basic"
  - "Date data type, Visual Basic"
  - "Visual Basic, data types"
  - "storage, allocation"
  - "Integer data type, Visual Basic data types"
  - "storage, space"
  - "Variant data types, supported types in Visual Basic"
  - "Char data type, Visual Basic data types"
  - "intrinsic data types"
  - "memory consumption, data types"
  - "single-precision numbers"
  - "data types [Visual Basic], order of storage"
  - "Long data type, supported types in Visual Basic"
  - "String data type, Visual Basic data types"
  - "storage order, data types"
  - "StructLayoutAttribute class, Visual Basic data type storage"
  - "scientific notation"
  - "Double data type, Visual Basic data types"
  - "Byte data type, Visual Basic data types"
  - "Object data type, supported types in Visual Basic"
  - "data types [Visual Basic], storage allocation"
  - "double-precision numbers"
  - "data types [Visual Basic], summary"
  - "dates [Visual Basic], data types"
  - "strings [Visual Basic], data types"
  - "memory consumption"
  - "storage order, controlling in Visual Basic"
  - "data types [Visual Basic], memory requirements"
ms.assetid: e975cdb6-64d8-4a4a-ae27-f3b3ed198ae0
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Data Type Summary (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

다음 표에서는 Visual Basic 데이터 형식과 각 형식이 지원하는 공용 언어 런타임 형식, 일반 저장소 할당 및 값 범위를 보여 줍니다.  
  
|Visual Basic 형식|공용 언어 런타임 형식 구조체|일반 저장소 할당|값 범위|  
|---------------------|----------------------|---------------|----------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|구현하는 플랫폼에 따라 다름|`True` 또는 `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1바이트|값 범위는 0에서 255까지\(부호 없음\)입니다.|  
|[Char](../../../visual-basic/language-reference/data-types/char-data-type.md)\(단일 문자\)|<xref:System.Char>|2바이트|값 범위는 0에서 65535까지\(부호 없음\)입니다.|  
|[날짜](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8바이트|값 범위는 0:00:00\(1년 1월 1일 자정\)에서 11:59:59 PM\(9999년 12월 31일\)까지 입니다.|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16바이트|값의 범위는 0에서 \+\/\-79,228,162,514,264,337,593,543,950,335\(\+\/\-7.9...E\+28\)<sup>†</sup>까지\(소수 부분이 없음\) 또는 0에서 \+\/\-7.9228162514264337593543950335까지\(소수 자릿수가 28개가 있음\)입니다.<br /><br /> 0이 아닌 숫자 중에서 최소 숫자는 \+\/\-0.0000000000000000000000000001\(\+\/\-1E\-28\)<sup>†</sup>입니다.|  
|[Double](../../../visual-basic/language-reference/data-types/double-data-type.md) \(배정밀도 부동 소수점\)|<xref:System.Double>|8바이트|값의 범위는 \-1.79769313486231570E\+308에서 \-4.94065645841246544E\-324<sup>†</sup>까지\(음수\)입니다.<br /><br /> 값의 범위는 4.94065645841246544E\-324에서 1.79769313486231570E\+308<sup>†</sup>까지\(양수\)입니다.|  
|[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4바이트|값의 범위는 \-2,147,483,648에서 2,147,483,647까지\(부호 있음\)입니다.|  
|[Long](../../../visual-basic/language-reference/data-types/long-data-type.md)\(정수\(Long\)\)|<xref:System.Int64>|8바이트|값의 범위는 \-9,223,372,036,854,775,808에서 9,223,372,036,854,775,807\(9.2...E\+18 <sup>†</sup>\)까지\(부호 있음\)입니다.|  
|[개체](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object>\(클래스\)|32비트 플랫폼에서 4바이트<br /><br /> 64비트 플랫폼에서 8바이트|`Object` 형식의 변수에는 모든 형식을 저장할 수 있습니다.|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1바이트|값의 범위는 \-128에서 127까지\(부호 있음\)입니다.|  
|[Short](../../../visual-basic/language-reference/data-types/short-data-type.md)\(정수\(Short\)\)|<xref:System.Int16>|2바이트|값의 범위는 \-32,768에서 32,767까지\(부호 있음\)입니다.|  
|[Single](../../../visual-basic/language-reference/data-types/single-data-type.md) \(단정밀도 부동 소수점\)|<xref:System.Single>|4바이트|값의 범위는 \-3.4028235E\+38에서 \-1.401298E\-45<sup>†</sup>까지\(음수\) 또는<br /><br /> 1.401298E\-45에서 3.4028235E\+38<sup>†</sup>까지\(양수\)입니다.|  
|[String](../../../visual-basic/language-reference/data-types/string-data-type.md) \(가변 길이\)|<xref:System.String>\(클래스\)|구현하는 플랫폼에 따라 다름|0에서 약 20억 개의 유니코드 문자입니다.|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4바이트|값의 범위는 0에서 4,294,967,295까지\(부호 없음\)입니다.|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8바이트|값의 범위는 0에서 18,446,744,073,709,551,615\(1.8...E\+19 <sup>†</sup>\)까지\(부호 없음\)입니다.|  
|[사용자 정의](../../../visual-basic/language-reference/data-types/user-defined-data-type.md)\(구조체\)|\(<xref:System.ValueType>에서 상속\)|구현하는 플랫폼에 따라 다름|구조체의 각 멤버는 데이터 형식에 의해 결정되고 다른 멤버의 범위와는 무관한 범위를 갖습니다.|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2바이트|값의 범위는 0에서 65,535까지\(부호 없음\)입니다.|  
  
 <sup>†</sup> *과학적 표기법*에서 "E"는 10의 거듭제곱을 나타냅니다.  따라서 3.56E\+2는 3.56 x 10<sup>2</sup>, 즉 356을 나타내고 3.56E\-2는 3.56 \/ 10<sup>2</sup>, 즉 0.0356을 나타냅니다.  
  
> [!NOTE]
>  텍스트를 포함하는 문자열에서는 <xref:Microsoft.VisualBasic.Strings.StrConv%2A> 함수를 사용하여 텍스트 형식을 다른 형식으로 변환하십시오.  
  
 선언문에서 데이터 형식을 지정 하는 것 외에 형식 문자를 사용 하 여 일부 프로그래밍 요소의 데이터 형식을 할 수 있습니다.  자세한 내용은 [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)를 참조하십시오.  
  
## 메모리 사용  
 기본 데이터 형식을 선언할 때 메모리 사용량이 일반 저장소 할당량과 같다고 가정하는 것은 위험합니다.  이는 다음과 같이 고려해야 할 사항이 있기 때문입니다.  
  
-   **저장소 할당.** 공용 언어 런타임에서 응용 프로그램이 실행되고 있는 플랫폼의 특성에 따라 저장소를 할당할 수 있습니다.  메모리에 여유 공간이 거의 없으면 선언된 요소가 가능한 서로 인접하도록 함께 묶입니다.  다른 경우에는 성능을 최적화하기 위해 자연스러운 하드웨어 경계에 메모리 주소를 맞출 수 있습니다.  
  
-   **플랫폼 너비.** 64비트 플랫폼에서의 저장소 할당은 32비트 플랫폼에서의 할당과 다릅니다.  
  
### 복합 데이터 형식  
 구조체나 배열과 같은 복합 데이터 형식의 각 멤버에는 같은 고려 사항이 적용됩니다.  단순히 형식 멤버의 일반 저장소 할당량을 모두 더하는 것만으로 필요한 메모리를 계산할 수는 없습니다.  또한 다음과 같은 다른 고려 사항도 적용됩니다.  
  
-   **오버헤드.** 일부 복합 형식에는 메모리가 추가로 필요합니다.  예를 들어, 배열은 배열 자체뿐 아니라 각 차원에 대해서도 메모리를 사용합니다.  32비트 플랫폼의 경우 현재 각 차원에 대해 기본적인 12바이트 외에 8바이트가 추가로 필요합니다.  64비트 플랫폼에서는 이 요구 사항이 두 배로 증가합니다.  
  
-   **저장소 레이아웃.** 메모리에서 저장소의 순서가 사용자의 선언 순서와 동일하다고 가정할 수 없습니다.  심지어 2바이트 또는 4바이트 경계와 같은 바이트 정렬을 가정할 수도 없습니다.  클래스나 구조체를 정의하는 중이며 해당 멤버의 저장소 레이아웃을 제어해야 할 경우 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 클래스나 구조체에 적용할 수 있습니다.  
  
### 개체 오버헤드  
 기본 또는 복합 데이터 형식을 참조하는 `Object`는 해당 데이터 형식에 포함된 데이터 외에 4바이트를 추가로 사용합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Strings.StrConv%2A>   
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)