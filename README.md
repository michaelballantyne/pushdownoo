# Pushdown OO (Version extracted from APAC second delievery)

This is just analytic engine without play framework. 

## Environment

### Scala 2.9.1 

The reason didn't move to 2.10: 
* StackOverflow error in Scala 2.10
* Code changes such as case class must have parameters
* Scala 2.9.1 works perfectly with Play 2.0.4

### JVM -- compiled successfully on jre.1.6.0.24. (not 1.7)

### Graphviz 

For converting to svg dyck state graph. (It will get choke on large dot files)

## Compile

	cd pdafordalvik
	ant compile
	ant jar
	

## Run
Still in `pdafordalvik` folder
	
	

	java -jar artifacts/PushdownOO_Exflow.jar org.ucombinator.dalvik.cfa.cesk.RunAnalysis [--k <number>] [--gc] [--lra] [--aco] [--godel] [--dump-graph] [--interrupt-after <number-of-states>] [--interrupt-after-time <number of minutes>] path/to/your/filename.apk
	
	e.g.
	java -jar artifacts/PushdownOO_Exflow.jar org.ucombinator.dalvik.cfa.cesk.RunAnalysis  --k 1 --gc --lra --aco --godel --dump-graph ./test/Bookworm.apk
	
### For Intent Fuzzer

	java -jar artifacts/PushdownOO_Exflow.jar org.ucombinator.dalvik.cfa.cesk.RunAnalysis  --k 1 --gc --lra --aco --godel --for-intent-fuzzer ./test/SmsReminder.apk