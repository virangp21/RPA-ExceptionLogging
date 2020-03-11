# RPA-ExceptionLogging
## Introduction

This is an example of logging additional exception details from RPA  project for better handling of exceptions and quicker issue resolution. By default UiPath provide Log Message activity to log details and we can use this to create our own workflow to log exception details. During development and debugging it is easier to see where exceptions are occurring via $exceptionActivityInfo object in local panel but that information is not available at run time. You may also have many files that are being called via Invoke Workflow activity so keeping track of where exception is occurring is very important. 

This LogException workflow will log these details. 

	-	File Exception Occurred in : There is no way to get this value dynamically so you have to pass this in as string when calling this workflow.
	-	Exception Message : It is very important to log this details to identify what  has caused the exception. Workflow checks if in_ExceptionMessage parameter is passed. If so it logs that otherwise it logs message from in_Exception object. 
	-	Exception caused by Method / Reflected Method : This is useful to find out which step within a large/complex workflow is causing the issue. This doesn't give exact activity name but gives information about underlying method that is failing and that is very helpful in pinpointing error. 
	-	Exception StackTrace : There is an optional boolean parameter to indicate  if stack trace logging is required. 
	-	Inner Exception Message : This becomes useful when exception is caused by method call up the chain. 



