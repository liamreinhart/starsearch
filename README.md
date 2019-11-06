# starsearch
program using multiple functions to average out the middle three scores from a five judge panel

  1 // Liam Reinhart
  2 // 8 November 2019
  3 // code to validate and calculate five scores by dropping the highest and lowest and taking the average of the remaining scores
  4 
  5 #include <iostream>
  6 #include <iomanip>
  7 using namespace std;
  8 
  9 void getJudgeData(double &performance);
 10 void calcScore(double, double, double, double, double);
 11 double findLowest(double, double, double, double, double);
 12 double findHighest(double, double, double, double, double);
 13 
 14 int main()
 15 {
 16   // variable declaration
 17   double s1, s2, s3, s4, s5;
 18 
 19   // call funciton getJudgeData() 5 times, 1 for each judge
 20   getJudgeData(s1);
 21   getJudgeData(s2);
 22   getJudgeData(s3);
 23   getJudgeData(s4);
 24   getJudgeData(s5);
 25 
 26   // call function calcScore() to get average
 27   calcScore(s1, s2, s3, s4, s5);
 28 
 29   return 0;
 30 }
 31 
 32 void getJudgeData(double &performanceScore)
 33   {
 34     // input
 35     cout << "Enter performance score (0-10) : ";
 36     cin  >> performanceScore;
 37 
 38     // input validation
 39     while (performanceScore < 0 || performanceScore > 10)
 40       {
 41         cout << "ERROR---ENTER SCORE WITHIN RANGE : ";
 42         cin  >> performanceScore;
 43       }
 44   }
 45 
 46 void calcScore(double s1, double s2, double s3, double s4, double s5)
 47   {
 48     // init
 49     cout.setf(ios::fixed);
 50     cout.setf(ios::showpoint);
 51     cout.precision(2);
 52 
 53     // input
 54     cout << "Average of the 3 scores is : ";
 55 
 56     // processing
 57     cout << ((s1 + s2 + s3 + s4 + s5) - findLowest(s1, s2, s3, s4, s5) - findHighest(s1, s2, s3, s4, s5)) / 3 << endl;
 58   }
 59 
 60 double findLowest(double s1, double s2, double s3, double s4, double s5)
 61   {
 62     double low;
 63                                                                                                                                                                                         
 64       if (s1 < s2 && s1 < s3 && s1 < s4 && s1 < s5)
 65         {
 66         low = s1;
 67         }
 68       else if (s2 < s1 && s2 < s3 && s2 < s4 && s2 < s5)
 69         {
 70         low = s2;
 71         }
 72       else if (s3 < s1 && s3 < s2 && s3 < s4 && s3 < s5)
 73         {
 74         low = s3;
 75         }
 76       else if (s4 < s1 && s4 < s2 && s4 < s3 && s4 < s5)
 77         {
 78         low = s4;
 79         }
 80       else if (s5 < s1 && s5 < s2 && s5 < s3 && s5 < s4)
 81         {
 82         low = s5;
 83         }
 84     return low;
 85   }
 86 
 87 double findHighest(double s1, double s2, double s3, double s4, double s5)
 88   {
 89     double high;
 90 
 91       if (s1 > s2 && s1 > s3 && s1 > s4 && s1 > s5)
 92         {
 93         high = s1;
 94         }
 95       else if (s2 > s1 && s2 > s3 && s2 > s4 && s2 > s5)
 96         {
 97         high = s2;
 98         }
 99       else if (s3 > s1 && s3 > s2 && s3 > s4 && s3 > s5)
100         {
101         high = s3;
102         }
103       else if (s4 > s1 && s4 > s2 && s4 > s3 && s4 > s5)
104         {
105         high = s4;
106         }
107       else if (s5 > s1 && s5 > s2 && s5 > s3 && s5 > s4)
108         {
109         high = s5;
110         }
111     return high;
112   }
                                                                                                                                                                                         
