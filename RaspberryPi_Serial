ser = serial.Serial('/dev/ttyACM0', 115200) 
                targetCoordinates = recv_data[0]
                fromArduino = 'C' 
                while fromArduino == 'C':
                    if not targetCoordinates:
                        ser.write('A'.encode()) 
                        fromArduino = ser.read()
                    else:
                        xCoord = targetCoordinates[0]
                        yCoord = targetCoordinates[1]
                        if(xCoord > 50):
                            ser.write('L'.encode())
                        elif(xCoord < -50):
                            ser.write('R'.encode())
                        elif(xCoord):
                            ser.write('F'.encode())
                        elif(yCoord):
                            ser.write('T'.encode())
                        elif((xCoord > -50) and (xCoord < 50)):
                            if(yCoord > 150):
                                ser.write('F'.encode())
                            elif(yCoord < -150):
                                ser.write('T'.encode())
                            else:
                                time.sleep(0.05)
                        else:
                            ser.write('A'.encode())

                    fromArduino = ser.read()
