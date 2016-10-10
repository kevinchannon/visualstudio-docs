---
title: "CA2134: Methods must keep consistent transparency when overriding base methods"
ms.custom: na
ms.date: 10/03/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-devops-test
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
caps.latest.revision: 9
manager: douge
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# CA2134: Methods must keep consistent transparency when overriding base methods
|||  
|-|-|  
|TypeName|MethodsMustOverrideWithConsistentTransparency|  
|CheckId|CA2134|  
|Category|Microsoft.Security|  
|Breaking Change|Breaking|  
  
## Cause  
 This rule fires when a method marked with the <xref:System.Security.SecurityCriticalAttribute?qualifyHint=False> overrides a method that is transparent or marked with the <xref:System.Security.SecuritySafeCriticalAttribute?qualifyHint=False>. The rule also fires when a method that is transparent or marked with the <xref:System.Security.SecuritySafeCriticalAttribute?qualifyHint=False> overrides a method that is marked with a <xref:System.Security.SecurityCriticalAttribute?qualifyHint=False>.  
  
 The rule is applied when overriding a virtual method or implementing an interface.  
  
## Rule Description  
 This rule fires on attempts to change the security accessibility of a method further up the inheritance chain. For example, if a virtual method in a base class is transparent or safe-critical, then the derived class must override it with a transparent or safe-critical method. Conversely, if the virtual is security critical, the derived class must override it with a security critical method. The same rule applies for implementing interface methods.  
  
 Transparency rules are enforced when the code is JIT compiled instead of at runtime, so that the transparency calculation does not have dynamic type information. Therefore, the result of the transparency calculation must be able to be determined solely from the static types being JIT-compiled, regardless of the dynamic type.  
  
## How to Fix Violations  
 To fix a violation of this rule, change the transparency of the method that is overriding a virtual method or implementing an interface to match the transparency of the virtual or interface method.  
  
## When to Suppress Warnings  
 Do not suppress warnings from this rule. Violations of this rule will result in a runtime <xref:System.TypeLoadException?qualifyHint=False> for assemblies that use level 2 transparency.  
  
## Examples  
  
### Code  
 [!CODE [FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../CodeSnippet/VS_Snippets_CodeAnalysis/fxcop.security.ca2134.methodsmustoverridewithconsistenttransparency#1)]  
  
## See Also  
 [Security-Transparent Code, Level 2](../Topic/Security-Transparent%20Code,%20Level%202.md)