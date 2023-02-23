ssh cs15lwi23atl@ieng6.ucsd.edu

git clone git@github.com:ConnortheFan/lab7.git

cd lab7/

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

nano ListExamples.java

> Change index1 into index2

<Ctrl-O> <Enter> <Ctrl-X>

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

git add ListExamples.java

git commit -m 'l'

git push
