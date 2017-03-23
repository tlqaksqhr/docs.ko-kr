---
title: "수학 함수(Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "수학 함수, Visual Basic"
  - "산술 연산, 수학 함수"
  - "수학 루틴"
  - "Atn 함수"
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# 수학 함수(Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

메서드는 <xref:System.Math?displayProperty=fullName> 클래스 삼각, 로그 및 기타 일반 수학 함수를 제공 합니다.  
  
## 설명  
 메서드를 다음 표에 나와 있는 <xref:System.Math?displayProperty=fullName> 클래스입니다.  Visual Basic 프로그램에서 사용할 수 있습니다.  
  
|.NET Framework 메서드|설명|  
|------------------------|--------|  
|<xref:System.Math.Abs%2A>|숫자의 절대 값을 반환합니다.|  
|<xref:System.Math.Acos%2A>|코사인을 적용했을 때 지정된 숫자가 나오는 각도를 반환합니다.|  
|<xref:System.Math.Asin%2A>|사인을 적용했을 때 지정된 숫자가 나오는 각도를 반환합니다.|  
|<xref:System.Math.Atan%2A>|탄젠트를 적용했을 때 지정된 숫자가 나오는 각도를 반환합니다.|  
|<xref:System.Math.Atan2%2A>|탄젠트를 적용했을 때 지정된 두 숫자의 몫이 나오는 각도를 반환합니다.|  
|<xref:System.Math.BigMul%2A>|전체 제품의 32 비트 숫자 두 개를 반환합니다.|  
|<xref:System.Math.Ceiling%2A>|보다 크거나 같으면 지정 된 최소 정수 값을 반환 합니다. `Decimal` 또는 `Double`.|  
|<xref:System.Math.Cos%2A>|지정된 각도의 코사인을 반환합니다.|  
|<xref:System.Math.Cosh%2A>|지정된 각도의 하이퍼볼릭 코사인을 반환합니다.|  
|<xref:System.Math.DivRem%2A>|두 32 비트 또는 64 비트 부호 있는 정수의 몫을 반환 하 고 나머지를 출력 매개 변수로 반환 합니다.|  
|<xref:System.Math.Exp%2A>|반환 e \(자연 로그의 밑\)를 지정 된 거듭제곱 발생 합니다.|  
|<xref:System.Math.Floor%2A>|지정 된 보다 작거나 같은 가장 큰 정수를 반환 합니다. `Decimal` 또는 `Double` 번호입니다.|  
|<xref:System.Math.IEEERemainder%2A>|번호를 지정 하는 지정된 된 숫자의 다른 숫자로 나눈 나머지를 반환 합니다.|  
|<xref:System.Math.Log%2A>|반환 자연 \(기본 e\) 지정 된 수 또는 지정 된 밑에서 지정 된 수의 로그의 밑입니다.|  
|<xref:System.Math.Log10%2A>|밑을 10으로 사용하여 지정된 숫자의 로그를 반환합니다.|  
|<xref:System.Math.Max%2A>|두 숫자 중 더 큰 숫자를 반환합니다.|  
|<xref:System.Math.Min%2A>|두 개의 숫자 중 더 작은 숫자를 반환합니다.|  
|<xref:System.Math.Pow%2A>|지정된 숫자의 지정된 거듭제곱을 반환합니다.|  
|<xref:System.Math.Round%2A>|반환 된 `Decimal` 또는 `Double` 값에 가장 가까운 정수 계열 값 또는 지정 된 수의 소수 자릿수에 반올림 합니다.|  
|<xref:System.Math.Sign%2A>|숫자의 부호를 나타내는 `Integer` 값을 반환합니다.|  
|<xref:System.Math.Sin%2A>|지정된 각도의 사인을 반환합니다.|  
|<xref:System.Math.Sinh%2A>|지정된 각도의 하이퍼볼릭 사인을 반환합니다.|  
|<xref:System.Math.Sqrt%2A>|지정된 숫자의 제곱근을 반환합니다.|  
|<xref:System.Math.Tan%2A>|지정된 각도의 탄젠트를 반환합니다.|  
|<xref:System.Math.Tanh%2A>|지정된 각도의 하이퍼볼릭 탄젠트를 반환합니다.|  
|<xref:System.Math.Truncate%2A>|지정 된 정수 부분을 계산 `Decimal` 또는 `Double` 번호입니다.|  
  
 한정자 없이 이러한 함수를 사용 하려면 가져오기는 <xref:System.Math?displayProperty=fullName> 네임 스페이스에 프로젝트 소스 파일의 위쪽에 다음 코드를 추가 하 여:  
  
```  
Imports System.Math  
```  
  
## 예제  
 다음 예제에서는 <xref:System.Math> 클래스의 <xref:System.Math.Abs%2A> 메서드를 사용하여 숫자의 절대 값을 계산합니다.  
  
```  
' Returns 50.3.  
Dim MyNumber1 As Double = Math.Abs(50.3)  
' Returns 50.3.  
Dim MyNumber2 As Double = Math.Abs(-50.3)  
```  
  
## 예제  
 다음 예제에서는 <xref:System.Math> 클래스의 <xref:System.Math.Atan%2A> 메서드를 사용하여 pi의 값을 계산합니다.  
  
```  
Public Function GetPi() As Double  
    ' Calculate the value of pi.  
    Return 4.0 * Math.Atan(1.0)  
End Function  
```  
  
## 예제  
 다음 예제에서는 <xref:System.Math> 클래스의 <xref:System.Math.Cos%2A> 메서드를 사용하여 각도의 코사인을 반환합니다.  
  
```  
Public Function Sec(ByVal angle As Double) As Double  
    ' Calculate the secant of angle, in radians.  
    Return 1.0 / Math.Cos(angle)  
End Function  
```  
  
## 예제  
 다음 예제에서는 <xref:System.Math> 클래스의 <xref:System.Math.Exp%2A> 메서드를 사용하여 승수로 거듭제곱하는 e를 반환합니다.  
  
```  
Public Function Sinh(ByVal angle As Double) As Double  
    ' Calculate hyperbolic sine of an angle, in radians.  
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0  
End Function  
```  
  
## 예제  
 다음 예제에서는 <xref:System.Math> 클래스의 <xref:System.Math.Log%2A> 메서드를 사용하여 숫자의 자연 로그를 반환합니다.  
  
```  
Public Function Asinh(ByVal value As Double) As Double  
    ' Calculate inverse hyperbolic sine, in radians.  
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))  
End Function  
```  
  
## 예제  
 다음 예제에서는 <xref:System.Math> 클래스의 <xref:System.Math.Round%2A> 메서드를 사용하여 가장 가까운 정수로 숫자를 반올림합니다.  
  
```  
' Returns 3.  
Dim MyVar2 As Double = Math.Round(2.8)  
```  
  
## 예제  
 다음 예제에서는 <xref:System.Math> 클래스의 <xref:System.Math.Sign%2A> 메서드를 사용하여 숫자의 부호를 결정합니다.  
  
```  
' Returns 1.  
Dim MySign1 As Integer = Math.Sign(12)  
' Returns -1.  
Dim MySign2 As Integer = Math.Sign(-2.4)  
' Returns 0.  
Dim MySign3 As Integer = Math.Sign(0)  
```  
  
## 예제  
 다음 예제에서는 <xref:System.Math> 클래스의 <xref:System.Math.Sin%2A> 메서드를 사용하여 각도의 사인을 반환합니다.  
  
```  
Public Function Csc(ByVal angle As Double) As Double  
    ' Calculate cosecant of an angle, in radians.  
    Return 1.0 / Math.Sin(angle)  
End Function  
```  
  
## 예제  
 다음 예제에서는 <xref:System.Math> 클래스의 <xref:System.Math.Sqrt%2A> 메서드를 사용하여 숫자의 제곱근을 계산합니다.  
  
```  
' Returns 2.  
Dim MySqr1 As Double = Math.Sqrt(4)  
' Returns 4.79583152331272.  
Dim MySqr2 As Double = Math.Sqrt(23)  
' Returns 0.  
Dim MySqr3 As Double = Math.Sqrt(0)  
' Returns NaN (not a number).  
Dim MySqr4 As Double = Math.Sqrt(-4)  
```  
  
## 예제  
 다음 예제에서는 <xref:System.Math> 클래스의 <xref:System.Math.Tan%2A> 메서드를 사용하여 각도의 탄젠트를 반환합니다.  
  
```  
Public Function Ctan(ByVal angle As Double) As Double  
    ' Calculate cotangent of an angle, in radians.  
    Return 1.0 / Math.Tan(angle)  
End Function  
```  
  
## 요구 사항  
 **클래스:** <xref:System.Math>  
  
 **네임스페이스:** <xref:System>  
  
 **어셈블리:** mscorlib\(mscorlib.dll\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>   
 <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>   
 <xref:System.Double.NaN>   
 [Derived Math Functions](../../../visual-basic/language-reference/keywords/derived-math-functions.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)