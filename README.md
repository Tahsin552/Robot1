  delayMicroseconds(2);
  digitalWrite(trigPin2, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin2, LOW);
  duration2 = pulseIn(echoPin2, HIGH);
  distancefront = duration2 * 0.034 / 2;
  Serial.print("Distance2: ");
  Serial.println(distancefront);
  digitalWrite(trigPin3, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin3, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin3, LOW);
  duration3 = pulseIn(echoPin3, HIGH);
  distanceright = duration3 * 0.034 / 2;
  Serial.print("Distance3: ");
  Serial.println(distanceright);
  if ((distanceleft <= 15 && distancefront > 15 && distanceright <= 15) || (distanceleft > 15 && distancefront > 15 && distanceright > 15))
  {
    digitalWrite(4, HIGH);
    digitalWrite(7, LOW);
    digitalWrite(8, HIGH);
    digitalWrite(12, LOW);
  }
  if ((distanceleft <= 15 && distancefront <= 15 && distanceright > 15) || (distanceleft <= 15 && distancefront > 15 && distanceright > 15))
  {
    digitalWrite(4, HIGH);
    digitalWrite(7, LOW);
    digitalWrite(8, LOW);
    digitalWrite(12, HIGH);
  }
  if ((distanceleft > 15 && distancefront <= 15 && distanceright <= 15) || (distanceleft > 15 && distancefront > 15 && distanceright <= 15) ||  (distanceleft > 15 && distancefront <= 15 && distanceright > 15) )
  {
    digitalWrite(4, LOW);
    digitalWrite(7, HIGH);
    digitalWrite(8, HIGH);
    digitalWrite(12, LOW);
  } 
}
 
