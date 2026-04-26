#!/bin/bash
# Script: Perform Arithmetic Operations

echo "Enter two numbers:"
read a b

echo "Addition: $((a+b))"
echo "Subtraction: $((a-b))"
echo "Multiplication: $((a*b))"
echo "Division: $((a/b))"



#!/bin/bash
# Script: Calculate Simple Interest and Compound Interest

echo "Enter Principal, Rate, Time:"
read p r t

si=$(echo "scale=2; ($p*$r*$t)/100" | bc)
ci=$(echo "scale=2; $p*(1+$r/100)^$t" | bc)

echo "Simple Interest: $si"
echo "Compound Interest: $ci"



#!/bin/bash
# Script: Check Leap Year

echo "Enter year:"
read y

if (( (y%4==0 && y%100!=0) || (y%400==0) ))
then
  echo "Leap Year"
else
  echo "Not a Leap Year"
fi



#!/bin/bash
# Script: Compare Two Strings

echo "Enter two strings:"
read s1 s2

if [ "$s1" = "$s2" ]
then
  echo "Strings are equal"
else
  echo "Strings are not equal"
fi



#!/bin/bash
# Script: Menu Driven Calculator using case

echo "Enter two numbers:"
read a b

echo "1.Add 2.Subtract 3.Multiply 4.Divide"
read ch

case $ch in
1) echo "Sum: $((a+b))" ;;
2) echo "Difference: $((a-b))" ;;
3) echo "Product: $((a*b))" ;;
4) echo "Division: $((a/b))" ;;
*) echo "Invalid choice" ;;
esac





#!/bin/bash
# Script: Employee Pay Calculation

echo "Enter basic salary:"
read basic

hra=$(echo "$basic*0.2" | bc)
da=$(echo "$basic*0.1" | bc)
gross=$(echo "$basic+$hra+$da" | bc)

echo "Gross Salary: $gross"





#!/bin/bash
# Script: Perform Directory Operations

echo "Current Directory:"
pwd

echo "Contents:"
ls

mkdir testdir
echo "Hello File" > testdir/file.txt

cp testdir/file.txt ~/

echo "File copied to home directory"







#!/bin/bash
# Script: Menu Driven Number Operations

echo "Enter number:"
read n

echo "1.Even/Odd 2.Prime 3.Palindrome 4.Armstrong"
read ch

case $ch in
1)
if ((n%2==0)); then echo "Even"; else echo "Odd"; fi
;;

2)
flag=0
for ((i=2;i<n;i++))
do
  if ((n%i==0)); then flag=1; fi
done
[ $flag -eq 0 ] && echo "Prime" || echo "Not Prime"
;;

3)
rev=0
temp=$n
while ((temp>0))
do
  r=$((temp%10))
  rev=$((rev*10+r))
  temp=$((temp/10))
done
[ $rev -eq $n ] && echo "Palindrome" || echo "Not Palindrome"
;;

4)
sum=0
temp=$n
while ((temp>0))
do
  r=$((temp%10))
  sum=$((sum+r*r*r))
  temp=$((temp/10))
done
[ $sum -eq $n ] && echo "Armstrong" || echo "Not Armstrong"
;;
esac




#!/bin/bash
# Script: Search Element in List

echo "Enter elements:"
read -a arr

echo "Enter element to search:"
read key

found=0
for i in "${arr[@]}"
do
  if [ "$i" = "$key" ]; then found=1; fi
done

[ $found -eq 1 ] && echo "Found" || echo "Not Found"








#!/bin/bash
# Script: Check File or Directory Exists

echo "Enter name:"
read name

if [ -d "$name" ]
then
  echo "Directory exists"
elif [ -f "$name" ]
then
  echo "File exists"
else
  mkdir "$name"
  echo "Created directory"
fi








#!/bin/bash
# Script: Count Lines, Words, Characters using grep/wc

echo "Enter filename:"
read file

echo "Lines: $(wc -l < $file)"
echo "Words: $(wc -w < $file)"
echo "Chars: $(wc -c < $file)"








#!/bin/bash
# Script: Display Specific File Types using egrep

ls | egrep "\.txt$|\.sh$"





#!/bin/bash
# Script: Replace Word using sed

echo "Enter file:"
read file

sed 's/old/new/g' $file





#!/bin/bash
# Script: Display Duplicate Lines

echo "Enter file:"
read file

sort $file | uniq -d







