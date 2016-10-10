---
title: "&lt;name&gt; is not a valid solution name."
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 79b7870d-16bd-4527-8ce6-ffb015e7e330
caps.latest.revision: 8
manager: douge
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# &lt;name&gt; is not a valid solution name.
This error generally occurs when the command `File.NewProject` has been entered in the **Command** window or **Find/Command** box with an incorrectly formatted value for the argument /sln:*solutionname*.  
  
### To correct this error  
  
1.  Re-type the command syntax and omit the optional argument /sln:*solutionname*. A unique solution name will automatically be generated.  
  
     —or—  
  
     Check that the solution name does not contain leading or trailing spaces and is not a reserved word. Reserved words include NUL, CON, AUX, COM*x*, or LPT*x*, where *x* is a digit 1-9.  
  
## See Also  
 [Command Window](../VS_IDE/Command-Window.md)