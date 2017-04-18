---
title: ".NET Framework의 숫자 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SIMD"
  - "System.Numerics.Vectors"
  - "벡터"
  - "과학적 컴퓨팅"
  - "복합"
  - "숫자"
  - "BigInteger"
ms.assetid: dfebc18e-acde-4510-9fa7-9a0f4aa3bd11
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# .NET Framework의 숫자
.NET Framework는 표준 숫자 정수 계열 및 부동 소수점 기본 형식과 지원 뿐만 <xref:System.Numerics.BigInteger>, 이론적 상한 또는 하 한이 없는 정수 형식 <xref:System.Numerics.Complex>, 복소수를 나타내는 형식 및의 SIMD 사용 벡터 형식 집합은 <xref:System.Numerics> 네임 스페이스입니다.  
  
 또한 System.Numerics.Vectors, SIMD 사용 형식 라이브러리에 vectory, NuGet 패키지로 릴리스 되었습니다.  
  
## <a name="integral-types"></a>정수 계열 형식 표  
 .NET Framework에서는&1;~8바이트 범위 길이의 부호 있는 정수와 부호 없는 정수를 둘 다 지원합니다. 다음 표에서는 정수 계열 형식 및 해당 크기 목록을 제공하고 부호가 있는지 여부를 표시하고 해당 범위를 문서화합니다. 모든 정수는 값 형식입니다.  
  
|형식|부호 있음/부호 없음|크기(바이트)|최소값|최대값|  
|----------|----------------------|--------------------|-------------------|-------------------|  
|<xref:System.Byte?displayProperty=fullName>|부호 없음|1|0|255|  
|<xref:System.Int16?displayProperty=fullName>|서명|2|-32,768|32,767|  
|<xref:System.Int32?displayProperty=fullName>|서명|4|-2,147,483,648|2,147,483,647|  
|<xref:System.Int64?displayProperty=fullName>|서명|9|-9,223,372,036,854,775,808|9,223,372,036,854,775,807|  
|<xref:System.SByte?displayProperty=fullName>|서명|1|-128|127|  
|<xref:System.UInt16?displayProperty=fullName>|부호 없음|2|0|65,535|  
|<xref:System.UInt32?displayProperty=fullName>|부호 없음|4|0|4,294,967,295|  
|<xref:System.UInt64?displayProperty=fullName>|부호 없음|9|0|18,446,744,073,709,551,615|  
  
 각 정수 계열 형식은 산술, 비교, 같음, 명시적 변환 및 암시적 변환 연산자의 표준 집합을 지원합니다. 각 정수에는 같음 비교 및 상대 비교를 수행하고, 숫자의 문자열 표시를 해당 정수로 변환하고, 정수를 해당 문자열 표시로 변환하는 메서드가 포함됩니다. 반올림 하 고 식별 두 정수의 더 작거나 더 큰 값에서 사용할 수 있는 같이 표준 연산자를 통해 처리 되는 것 이외의 몇몇 추가적인 수치 연산을 <xref:System.Math> 클래스입니다. 사용 하 여 정수 값의 개별 비트를 사용할 수도 있습니다는 <xref:System.BitConverter> 클래스입니다.  
  
 부호 없는 정수 형식은 CLS와 호환되지 않습니다. 자세한 내용은 참조 [언어 독립성 및 언어 독립적 구성 요소](../../docs/standard/language-independence-and-language-independent-components.md)합니다.  
  
## <a name="floating-point-types"></a>부동 소수점 형식  
 .NET Framework에는 다음 표에 나열된 세 가지 기본 형식 부동 소수점 형식이 포함됩니다.  
  
|형식|크기(바이트)|최소|Maximum|  
|----------|-----------------------|-------------|-------------|  
|<xref:System.Double?displayProperty=fullName>|9|-1.79769313486232e308|1.79769313486232e308|  
|<xref:System.Single?displayProperty=fullName>|4|-3.402823e38|3.402823e38|  
|<xref:System.Decimal?displayProperty=fullName>|16|-79,228,162,514,264,337,593,543,950,335|79,228,162,514,264,337,593,543,950,335|  
  
 각 부동 소수점 형식은 산술, 비교, 같음, 명시적 변환 및 암시적 변환 연산자의 표준 집합을 지원합니다. 각 형식에는 같음 비교 및 상대 비교를 수행하고, 부동 소수점 수의 문자열 표시를 변환하고, 부동 소수점 수를 해당 문자열 표시로 변환하는 메서드가 포함됩니다. 사용할 수 있는 일부 추가적인 수치, 대 수 및 삼각 연산은 <xref:System.Math> 클래스입니다. 개별 비트를 사용할 수도 있습니다 <xref:System.Double> 및 <xref:System.Single> 사용 하 여 값의 <xref:System.BitConverter> 클래스입니다. <xref:System.Decimal?displayProperty=fullName> 구조에는 자체 메서드가 <xref:System.Decimal.GetBits%2A?displayProperty=fullName> 및 [Decimal.Decimal (Int32\<xref:System.Decimal.%23ctor%28System.Int32%5B%5D%29?displayProperty=fullName>10 진수 값을 사용 하는 것의 개별에 대 한 몇 가지 추가적인 수치 연산을 수행 하는 것에 대 한 메서드의 자체 집합 뿐만 아니라 비트입니다.  
  
 <xref:System.Double> 및 <xref:System.Single> 형식은 기본적으로 정확 하지 않은 (예: 태양계에서 두 별 사이의 거리) 값 및는 높은 수준의 전체 자릿수와 반올림 오류가 적을 필요 없는 응용 프로그램에 대 한 사용 해야 하는 데 사용 됩니다. 이 방법을 사용할지는 <xref:System.Decimal?displayProperty=fullName> 큰 되는 경우에 대 한 정밀도 필요한 형식과 반올림 오류가 없는 것이 좋은 경우  
  
## <a name="biginteger"></a>BigInteger  
 <xref:System.Numerics.BigInteger?displayProperty=fullName>는 이론상 값에 상한이나 하한이 없는 임의로 큰 정수를 나타내는 변경할 수 없는 형식입니다. 메서드는 <xref:System.Numerics.BigInteger> 형식 매우 유사 다른 정수 계열 형식입니다.  
  
## <a name="complex"></a>복합  
 <xref:System.Numerics.Complex> 형식은 복소수, 즉, 사용 하 여 숫자 실수 및 허수 부분을 나타냅니다. 이 형식은 산술, 비교, 같음, 명시적 변환 및 암시적 변환 연산자의 표준 집합과 수치, 대수 및 삼각 메서드를 지원합니다.  
  
## <a name="simd-enabled-vector-types"></a>SIMD 사용 벡터 형식  
 <xref:System.Numerics> 네임 스페이스는.NET Framework에 대 한 SIMD 사용 벡터 형식 집합을 포함 합니다. SIMD(Single Instruction Multiple Data) 연산을 통해 몇몇 연산은 하드웨어 수준에서 병렬 처리될 수 있습니다. 이 덕분에 벡터를 통해 계산을 수행하는 수치, 공학용 및 그래픽 앱의 성능이 크게 향상됩니다.  
  
 .NET Framework의 SIMD 사용 벡터 형식은 다음과 같습니다.  또한 System.Numerics.Vectors에는 평면 형식과 쿼터니언 형식이 있습니다.  
  
-   <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, 및 <xref:System.Numerics.Vector4> 형식인 2, 3 및 4 차원 벡터 형식의 <xref:System.Single>합니다.  
  
-   두 행렬 형식 <xref:System.Numerics.Matrix3x2>, 3x2 행렬; 나타내는 및 <xref:System.Numerics.Matrix4x4>, 4x4 행렬을 나타냅니다.  
  
-   <xref:System.Numerics.Plane> 및 <xref:System.Numerics.Quaternion> 형식입니다.  
  
 SimD 사용 벡터 형식은 비SimD 사용 하드웨어 및 JIT 컴파일러에서 이 형식을 사용할 수 있는 IL에서 구현됩니다. SIMD 지침을 활용하려면 64비트 앱을 관리 코드에 대한 새로운 64비트 JIT 컴파일러로 컴파일해야 합니다. 이 관리 코드는 .NET Framework 4.6과 함께 포함되어 있으며 x64 프로세서를 대상으로 지정할 때 SIMD 지원을 추가합니다.  
  
 SIMD로 다운로드할 수도 있습니다는 [NuGet 패키지](http://www.nuget.org/packages/System.Numerics.Vectors)합니다.  NuGET 패키지에도 일반 <xref:System.Numerics.Vector%601> 기본 숫자 형식의 벡터를 만들 수 있도록 구조입니다. (기본 숫자 형식에서 모든 숫자 형식이 포함 되는 <xref:System> 네임 스페이스를 제외 하 고 <xref:System.Decimal>.) 또한는 <xref:System.Numerics.Vector%601> 구조 라이브러리 벡터를 작업할 때 호출할 수 있는 편리한 메서드를 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 주요 사항](../../docs/standard/application-essentials.md)