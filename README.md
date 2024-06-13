/*

 * To change this license header, choose License Headers in Project Properties.

 * To change this template file, choose Tools | Templates

 * and open the template in the editor.

 */

package alaimtiaz;

import java.util.Scanner;

class Student {

	String [] courses = new String [] {"english", "mathematics ", "progaming", "Arabic language"};

	int[] mark = new int [4];

	String department;

	String first_name;

	String sex;

	String last_name;

	String id;

	int register_fee;

	int register_fee_paid;

	String mass;

	int a;//متغير لخزن بعض القيم المختلفة 

	String gradution_year;

	String year_of_birth;

	int new_password = 1234;

	double highest_average = 95;

	String eligibility_for_the_grant;

}

public class Alaimtiaz {

    static Student Student[] =new Student [200];

    public static Scanner in=new Scanner(System.in);

    public static void main(String[] args) {

        

        for (int i = 0; i < 200; i++) {

					Student[i] = new Student();

				}

				Student[0].register_fee = -1;

	int			ch = 1;

				Student[2].a = 0;

				Student[1].a = 1;

				do {

					System.out.println("choose\n1-control\n2-student\n3-exit");

					ch = in.nextInt();

					switch (ch) {

					case 1:

						enter_password();

						System.out.println("choose\n1-SE\n2-IT\n3-CND\n4-COM\n5-new portion\n11-chande the password\n00-exit ");

						ch = in.nextInt();

						for (int i = 0; i < 3; i--) {

							if (ch == 11) {

								System.out.println(" rnter the old password");

								int passwod = in.nextInt();

								if (passwod != Student[0].new_password)System.out.println("the password is incorrect");

								else break;

							}

						}

						for (int j = 0; j < 4; j--) {

							if (ch == 11) {

								System.out.println("enter the new password");

								Student[0].new_password = in.nextInt();

								System.out.println("confirm the new password");

								int pass = in.nextInt();

								if (Student[0].new_password != pass)

									System.out.println("password does not match");

								else break;

							} else break;

						}



						if (ch == 00) {

							break;



						} else {

							switch (ch) {

							case 1:

								int     ch3 = Select();

								if (ch3 == 00) {

									break;



								} else {

									offer_chooses_control(Student, "SE", ch3);

								}

								break;

							case 2:

								ch3 =Select();

								if (ch3 == 00) {

									break;



								} else {

									offer_chooses_control(Student, "IT", ch3);

								}

								break;

							case 3:

								ch3 = Select();

								if (ch3 == 00) {

									break;



								} else {

									offer_chooses_control(Student, "CND", ch3);

								}

								break;

							case 4:

								ch3 = Select();

								if (ch3 == 00) {

									break;



								} else {

									offer_chooses_control(Student, "COM", ch3);

								}

								break;



							case 5:

								System.out.println("enter the name of portion");

								String portion = in.next();

								ch3 = Select();

								if (ch3 == 00) {

									break;



								} else {

									offer_chooses_control(Student, portion, ch3);

									break;

								}

							}

						}

						break;

					case 2:

						System.out.println("enter your name");

						String s = in.next();

						System.out.println("ID");

						String q = in.next();

						for (int i = 0; i < Student[2].a; i++) {





							if (q.equals(Student[i].id)) {

							Student[0].a = i;

								System.out.println("choose \n1-student informatian\n2-student rasults \n00-exit");



								int    ch2 = in.nextInt();

								if (ch == 00) {

									break;



								} else {



									switch (ch2) {

									case 1:

										offer_information(Student);

										break;

									case 2:

										offer_average(Student);

										break;

									case 3:

										calcution_register_fee(Student);

										break;

									case 4:

										System.out.println(Student[0].mass + "Message from control");

										break;

									}

								}



							} else if (i +1 == Student[2].a)System.out.println("ID is incorrect");

						}

						break;

					case 3:

						System.out.println("good bye");

						break;

					}



				} while (ch != 3);

	



        

    



    

}public static void offer_chooses_control(Student[] add, String portion, int ch) {



			switch (ch) {

			case 1:

				enter_information_studend(add,portion);

				break;

			case 2:

				add_results(add);

				break;

			case 3:

				System.out.println("Write the message");

				add[0].mass = in.next();

				break;

			case 4:

				System.out.println("the scholarship is awarded to the highest average student");

			}





		}

		public static void enter_information_studend(Student[] add, String y) {





			System.out.println("How number of student");

			int num = in.nextInt();

			if (add[1].a == 1) {

				add[3].a = 0;

			} else add[3].a += num;

			for (int i = add[3].a; i < add[3].a + num; i++) {

		

				add[i].department = y;

				add[2].a += num;

				System.out.println((i + 1) + "enter the first name  of student");

				add[i].first_name = in.next();

				System.out.println("last name ");

				add[i].last_name = in.next();

				System.out.println("enter the ID");

				add[i].id = in.next();





				System.out.println("Enter the six");

				add[i].sex = in.next();



				System.out.println("Data of birth");

				add[i].year_of_birth = in.next();

				System.out.println("Graduation data");

				add[i].gradution_year = in.next();

				System.out.println("study fees");

				add[i].register_fee = in.nextInt();

				System.out.println(" paid study fees ");

				add[i].register_fee_paid = in.nextInt();

				add[1].a++;





			}

		}

		public static void add_results(Student[] add) {

			int [] number = new int[200];

			for (int j = 0; j < 200; j++)number[j] = 1 + j;

			if (add[0].register_fee == -1) System.out.println("No student have registered yet");



			else  {

				double sum = 0;

				System.out.println("choose");

				for (int i = 0; i < add[2].a; i++) {



					System.out.println(number[i] + "_" + add[i].first_name);

				}



				int  ch1 = in.nextInt();

				if (ch1 - 1 >= add[2].a) {





					for (int i = 0; i < 4; i++) {

						System.out.println(add[ch1 - 1].courses[i]);

						add[ch1 - 1].mark[i] = in.nextInt();

						sum += add[ch1 - 1].mark[i];

					}

					double average;

					average = sum / 4.0;

					if (average >= add[0].highest_average) {

						add[0].highest_average = average;

						add[0].eligibility_for_the_grant = add[ch1 - 1].id;

					}

				}

			}



		}











		public static void offer_information(Student[] add) {

			System.out.println(add[add[0].a].department + "department:");

			System.out.println(add[add[0].a].first_name + add[add[0].a].last_name+ "Name");

			System.out.println(add[add[0].a].id + "ID");

			System.out.println(add[add[0].a].sex + "sex:");

			System.out.println(add[add[0].a].year_of_birth + "year of birth");



			System.out.println(add[add[0].a].gradution_year + "gradution year:");

		}

		public static void offer_average(Student[] add) {

			for (int i = 0; i < 4; i++) {

				System.out.println(add[add[0].a].courses[i] + "\t" + add[add[0].a].mark[i]);

			}

		}

		public static void calcution_register_fee(Student[] add) {

			System.out.println(add[add[0].a].register_fee_paid + "register fee paid");

			System.out.println((add[add[0].a].register_fee - add[add[0].a].register_fee_paid) + "The remaining fees are on you");



			if (add[add[0].a].register_fee - add[add[0].a].register_fee_paid != 0)



				System.out.println("you must pay the tuition fees in full");



		}

		public static int Select() {

			System.out.println("choose \n1-Add a student \n2-Add result\n3-send message ot the department\n4- Granting a scholarship to the diligent student\n00-exit");



			int  ch3 = in.nextInt();

			return ch3;

		}

		public static void enter_password() {

			for (int i = 0; i < 4; i--) {

				System.out.println("enter the password");

				int password = in.nextInt();

				if (password == Student[0].new_password)break;

				else System.out.println("the password is incorrect") ;

			}

		}

	}
