// Define pins for each segment (a-g) and the common pin
const int a = 2;
const int b = 3;
const int c = 4;
const int d = 5;
const int e = 6;
const int f = 7;
const int g = 8;
const int common = 9;

void setup() {
  // Set pins as output
  pinMode(a, OUTPUT);
  pinMode(b, OUTPUT);
  pinMode(c, OUTPUT);
  pinMode(d, OUTPUT);
  pinMode(e, OUTPUT);
  pinMode(f, OUTPUT);
  pinMode(g, OUTPUT);
  pinMode(common, OUTPUT);
}

void loop() {
  // Define arrays for each number
  int numbers[10][7] = {
    {1,1,1,1,1,1,0}, // 0
    {0,1,1,0,0,0,0}, // 1
    {1,1,0,1,1,0,1}, // 2
    {1,1,1,1,0,0,1}, // 3
    {0,1,1,0,0,1,1}, // 4
    {1,0,1,1,0,1,1}, // 5
    {1,0,1,1,1,1,1}, // 6
    {1,1,1,0,0,0,0}, // 7
    {1,1,1,1,1,1,1}, // 8
    {1,1,1,0,0,1,1}  // 9
  };

  // Loop through each number and display it
  for (int i = 0; i < 10; i++) {
    displayNumber(numbers[i]);
    delay(1000); // Change this delay to adjust the display rate
  }
}

// Function to display a number
void displayNumber(int num[]) {
  digitalWrite(common, LOW); // Turn on the common cathode/anode
  digitalWrite(a, num[0]);
  digitalWrite(b, num[1]);
  digitalWrite(c, num[2]);
  digitalWrite(d, num[3]);
  digitalWrite(e, num[4]);
  digitalWrite(f, num[5]);
  digitalWrite(g, num[6]);
  digitalWrite(common, HIGH); // Turn off the common cathode/anode
}

