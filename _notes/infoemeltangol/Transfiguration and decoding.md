# Transfiguration(Signal conversion) and coding
--- 

### Concepts of analogue and digital signal, examples for their use
 - analogue
	 - An analogue signal is a continuous signal, which varies continuously with what it represents within a defined range, and time interval. Its domain of interpretation and its set of values are infinite. 
	 - Some examples: 
		 - traditional clock (the hands change with the time), 
		 - traditional speedometer (the hands change with the the pressure on the accelerator)
		 - conventional thermometer (the mercury rises with the temperature)
		 - hourglass (the sand drops down from the top to the bottom over time)
 - digital
	- With digital signals we only use numbers and we only extract signal in a finite interval, such that we can properly and efficiently process it for our needs (analogue signal is basically infinite and we of course cannot process infinite units in a finite time). 
	- digital signal always needs to be encoded and decoded between the sender and receiver because computers can only read digital signal properly, while it has to be sent through analogue channels like optical or copper cables, wireless connections etc.
	
--- 
### Difference and characteristics of analogue and digital signals
 1. Representation: 
	 - analogue represents information in a continuous way which can take any value in a given range. 
	 - On the other hand digital signal represents information using discrete values or digits, typically in binary form (zeroes and ones)
 2. Nature of signal
	 - Analogue signals are continuous and smooth, resembling a wave-like form.
	 - Digital signals on the other hand are discrete step-like, consisting of distinct separate levels for example continuous changes in voltage can be interpreted as ones and zeros.
3. Signal quality
	- Analog signals are susceptible to noise and distortion during transmission or processing, which can degrade the quality of the signal.
	- Digital signals on the other hand have more discrete step-like structure, and are more resistant to noise
4. Signal processing
	- For processing analogue signals you need analogue circuits and devices, such as amplifiers and filters
	- While for digital you also need analogue to digital conversion and digital to analogue conversion if you want to transport them
5. storage and reproduction
	- Analogue signals typically recorded and then converted into digital signal, for storage, and because we cannot store infinite amount of signals, we cannot really reproduce the whole signal fully, at most to a level which is good enough for the task
	- On the other hand digital signal can be stored more easily, copied and reproduced without any significant loss of quality
	
---
### The digitalisation of analogue signals
- 1. Sampling
	-  If an analogue signal needs to be converted into digital, it is done by so-called "sampling": at certain intervals (like, for sounds or images) a "sample" of the signal state is taken and stored digitally (from a pool of infinite amount of analogue signal).
	- This signal can take an infinite number of values along the y-axis withing the given range
	- the range of interpretation is reduced, since we cannot store infinite amount of signals
- 2. Quantization
	- Quantization is the transformation of infinitely many possible values into finite values that are rounded to a selected value (like integers, decimal numbers and many more).
	- The quantization process produces the digitized signal.
	- During quantization, the measurement range is divided into finite intervals, and signal values are set within it.
	- The value established on the basis of the sample values are decreased in some cases increases i.e. the quantization adds noise to the original signal.
- 3. Encoding
	- encoding is an important part of converting the analogue signal, since computers need a format that they can efficiently process.
	- encoding converts the extracted signal into binary form by assigning it a series of ones and zeroes.
- Types:
	- PCM - assigns a unique code for each quantization level
	- DPCM - a code is assigned to the deviation from the previous sample
	- Predicted DPCM - describes the deviation from the expected value based on the previous sample series
	
---
### The law of sampling
- Shannon formulated the law of how often a continuous signal should be sampled to recover the original signal from the sampled signal sequence. Based on Shannon's law, if we want the samples to properly represent the spectrums component with the largest frequency, the sampling frequency has to be at least twice the size of the spectrums component's with the largest frequency.
	- For Example, the human ear can hear up to 20 000 hz and the most common sampling frequency of audio signals(via microphone), is 44 000khz because it is at least twice as larger than 20 000khz, so it must represent the whole 20 000khz spectrum properly, so that it could be turned back into analogue signal without issues.
	
---
### Image digitisation 
-  the visible image is essentially analogue information. 
-  the first step in the computer processing of images is the processing the visual light of an image into digits (digitisation). This is done by scanners and digital cameras.
- types
	- Black-and-white scanning: if the reflected light intensity is below a certain limit, the pixel is black (0), otherwise white (1).
	- Greyscale scanning: corresponds to a shade of grey depending on the intensity of the reflected light. The color of a point can be assigned from 0 to 255 (256 shades of grey).
	- Colour scanning: the colour filters of the sensors breaks down the reflected "mixed colour" light into a mix of red (R), green (G) and blue (B) values, so that the rgb values transmitted to the computer shows a single color. There is a set of 255 shades for each red green blue color (255<sup>3</sup> ≈ 16 million colours).
	- The quality of the digitised image also depends on the resolution of the scanner, measured in DPI (dots per inch, or the number of pixels per inch).
		- hardware (real) resolution: what the scanner is capable of through its optical system
		- software resolution (interpolated) : increasing the number of pixels by calculation
-  The digital camera also produces a raster image.
	- by changing the exposure time i.e.: how long the lens is opened and how long the cameras light censor allowed to receive light, the light censor's millions of tiny light sensitive cells detect light.
	- before the light touching the sensor, the image is altered with different filters usually 50% green, 25% red and 25% blue.
	- with the help of these filters and light sensor, each cells value is digitized, saved, and stored into series of rgb values, with the place of each pixel within the matrix also saved
	- the resolution of an image is the multiple of vertical (rows) and horizontal lines (columns) i.e. 1920 * 1080
	
---
### Sound digitisation
- steps are very similar to other analogue signal digitisation
- sound also has to be encoded and decoded when transporting the data between computers
- encoding of sound signal is done by a ADC module (analogue to digital converter) 
- decoding is done by a DAC module (digital to analogue converter)
- Shannon's law applies here as well. That's why CD quality is at least 44100 hz commonly
- Another characteristic that determines the quality of sound is the bit depth. Bit depth determines how much of the audible spectrum (from about 20 Hz to 18-20000 Hz) we can process as computer data.

---
### Tools for digitisation
- Scanner
- Digitising table
- Photo camera
- Video camera
- Microphone

---
### The concepts of data and data volume in informatics
- definition of data:
	- In computer science data is defined as a set or sequence of signals represented in some kind of signalling system that can be recorded, processed and then displayed i.e.: interpreted by some computing device. Data can be stored in any form, which we can understand.
- definition of data volume
	- data volume is a quantity that measures the number of signals in a chosen signalling system and corresponds to a unit of measure, which is finite a measure. 
	
---
### Units of measurement used in informatics and their characteristics
- The unit of the data is 1 bit (binary digit - 0/1). 1 byte = 8 bits, the conversion from 1024: KiB (kibibyte), MiB (mebibyte), GiB (gibibyte), TiB (tebibyte), PiB (pebibyte)... Or the more commonly used 1000 conversion: kB (kilobyte), MB (megabyte), GB (gigabyte), TB (terabyte), PB (petabyte), EB (exabyte).
- some conversions for reference
	- 1 GB = 8 Gbit = 1 000 MB = 8 000 Mbit = 1 000 000 kB = 8 000 000 kbit = 1 000 000 000 B = 8 000 000 000 bit
	- 1 GiB = 1024 MiB = 1 048 576 KiB = 1 073 741 824 B = 8 589 934 592 bi
	- The example above shows how much difference there can be between a conversion of 1000 and 1024 for larger amounts of data. This is often exploited, for example, by hard drive, ssd etc. manufacturers or Internet service providers. This is why, for example a 1 TB hard disk is actually only 976 GiB, even less after partitioning, and you don't actually get the full 1 TB of space.
	
---
### Binary number notation method and its importance in computer science
- representing integer numbers (on 1 byte, 8 bits):
	- A limited number of bits can be used to represent numbers.
	- integers in binary are reparented as 2<sup>1</sup>, 2<sup>2</sup>, 2<sup>3</sup>, 2<sup>4</sup>, etc.
		- for example starting from 2<sup>0</sup>, all the le 0 1 0 0 1 1 1 1 equals to 79 as 1 + 2 + 4 + 8 + 64 = 79 (from right to left, counting each 1, way to 2<sup>7</sup> )
		- To convert a number into a number base 10, we need to add them together.
	- The numbers can be divided into two parts:
		- signed: (+ or -) so from -128 to +128 thus we get the 0-255 range on 1 byte
		- unsigned: (+ only) from 0-255 range on 1 byte
	- representing integers is not limited to 8 bit, it can even be 32 bit.
- Representing real or floating point numbers
	- Often, we are not able to represent an exact value, so we will treat it as an approximate value.
	- The byte where the number is handled is divided into two parts and with 1 bit if it's negative or positive number: 
		mantissa
			is the fractional or decimal part of a logarithm or a floating-point number.
--- 
### Forms of binary character representation, structure and characteristics of code tables (ASCII, UNICODE)
- coding: when according to sets of rules, converting characters from a set to another set like: from ASCII to UNICODE
- types:
	- reversable
	- irreversible
- examples of code systems/sets: morse, punch card, digitising sounds or images
- character sets:
	- CCITT - This is the very first character set that allowed 32 characters to be represented. 
	- ASCII –  Contains all the letters used in the English alphabet, as well as the most common punctuation marks. The character set contains 128 characters. 
	- UNICODE - An international standard, includes characters from most languages, and is based on 16 bit, which is around 100 000 characters
	- UTF-8 – In contrast to the full UTF-32 encoding, which takes up 4 bytes per character, the more compact (1 byte) UTF-8 encoding is the most common. UTF-8 is a variable-length encoding (8 to 64 bits) that represents the Unicode character table. It is fairly common on Linux systems, but on Microsoft Windows upwords of xp is also fully supported. The IETF (Internet Engineering Task Force) Internet protocol demands, while using the protocol, utf-8 must be included in the possible character sets.
	
---
### The Conversion between binary, decimal, and hexadecimal number systems
- **Converting from binary to decimal (example number is 18)**
	1. Write down the binary number: 18 (in binary, it is written as 10010).
	2. Assign a positional value to each digit in the binary number, starting from the right and increasing by powers of 2 (from right to left): 2^0, 2^1, 2^2, 2^3, 2^4.
	3. Multiply each digit of the binary number by its corresponding positional value and sum up the results.
	    - 0 * 2^0 = 0
	    - 1 * 2^1 = 2
	    - 0 * 2^2 = 0
	    - 0 * 2^3 = 0
	    - 1 * 2^4 = 16
	4. Add up the results: 0 + 2 + 0 + 0 + 16 = 18.

- **converting from decimal to binary**
	1. Start with the decimal number you want to convert.
	2. Divide the decimal number by 2 and note down the quotient and the remainder.
	3. Take the quotient from the previous step and divide it by 2 again. Note down the new quotient and remainder.
	4. Repeat step 3, dividing each new quotient by 2 until the quotient becomes 0.
	5. Write down the remainders in reverse order. The resulting sequence of remainders is the binary representation of the original decimal number.
	- For example, let's convert the decimal number 18 to binary:
		- Step 1: Start with 18. 
		- Step 2: Divide 18 by 2. The quotient is 9 and the remainder is 0. 
		- Step 3: Divide 9 by 2. The quotient is 4 and the remainder is 1. 
		- Step 4: Divide 4 by 2. The quotient is 2 and the remainder is 0. 
		- Step 5: Divide 2 by 2. The quotient is 1 and the remainder is 0. 
		- Step 6: Divide 1 by 2. The quotient is 0 and the remainder is 1.
	- Writing down the remainders in reverse order gives us the binary representation:
		- 18 (decimal) = 10010 (binary)

- **converting from decimal to hexadecimal**
	1. Divide the decimal number by 16.
	2. Write down the remainder, which represents the least significant digit in hexadecimal.
	3. Divide the quotient from the previous step by 16.
	4. Write down the remainder obtained in Step 3.
	5. Repeat Steps 3 and 4 until the quotient becomes zero.
	6. The hexadecimal representation of the decimal number is obtained by writing the remainders obtained from the bottom-up.
	- Here's an example to convert the decimal number 137 to hexadecimal:
		1. 137 ÷ 16 = 8 remainder 9 (Write down 9)
			- to get back the remainder, do this.
				- for example 137 / 16 = 8.5625 
				- subtract the integer 8, you get 5625
				- now multiply back this number by 16
				- you get 9, now you have the remainder
		1. 8 ÷ 16 = 0 remainder 8 (Write down 8)
		2. The remainders obtained are 8 and 9. Therefore, the decimal number 137 is equivalent to the hexadecimal number 89.
	- It's important to note that if any of the remainders obtained in the process is greater than 9, it is represented using letters in hexadecimal. For example, 10 is represented as 'A', 11 as 'B', and so on.

- **Converting from hexadecimal to decimal**
	- To convert a hexadecimal number to decimal, you can use the positional notation system. Each digit in the hexadecimal number represents a certain value, and you multiply that value by the corresponding power of 16.
	- steps
		1. Assign decimal values to each hexadecimal digit: 
		    - 0 = 0
		    - 1 = 1
		    - 2 = 2
		    - 3 = 3
		    - 4 = 4
		    - 5 = 5
		    - 6 = 6
		    - 7 = 7
		    - 8 = 8
		    - 9 = 9
		    - A = 10
		    - B = 11
		    - C = 12
		    - D = 13
		    - E = 14
		    - F = 15
		2. Starting from the rightmost digit, multiply each digit by 16 raised to the power of its position (counting from 0 for the first digit from the right).
		3. Sum up the results of each multiplication.
	- For example, let's convert the hexadecimal number "3A" to decimal:
		1. 3A = (3 * 16^1) + (A * 16^0)
		1. Since A represents the decimal value 10:
		-  3A = (3 * 16^1) + (10 * 16^0)
		2. Simplifying the equation:
		- 3A = (3 * 16) + 10
		- 3A = 48 + 10
		- 3A = 58
		- Therefore, the hexadecimal number 3A is equivalent to the decimal number 58.

- **converting from binary to hexadecimal**
	- you have to divide the binary numbers in to groups of four from the right and evaluate each of them separately, and just determine if they are for example 11 than it is B if is 15 its F

- **converting from hexadecimal to binary**
	- you have to evaluate each hexadecimal letter individually. 
		- for example: BC1 
			- B = 11 --> 1011 (first from the left)
			- C = 12 --> 1010 (second from the left)
			- 1 = 1 --> 0001 (third form the left)
			- and so you answer will be 1011 1010 0001
			
---
### The basic operations possible with binary numbers are
- Addition: 
	- how to do it: https://www.khanacademy.org/math/algebra-home/alg-intro-to-algebra/algebra-alternate-number-bases/v/binary-addition
	- you just add numbers together, if a addition is larger then 1 than you convert that number into binary, and write its most right letter down, and carry those ones that are still left, and do this until there is nothing more to add. if this number is for example 3 than you'll write 1 and carry over the 1 above which there is no numbers. 
- Subtraction:
	- how to do it : https://www.youtube.com/watch?v=S9LJknZTyos
	- when 1-1 = 0 or 1-0 = 1, it is good, but when there's 0-1 you have to borrow from the nearest 1 from the left.
		- for example you don't have ones until 8. then you take the 8 destroy it, create two 4-s then destroy one of the 4-s end create 2 4-s, then again destroy one of the 2-s and create 2 1-s, and finally you are done with borrowing, and you can properly subtract without getting negative numbers
		- you cannot subtract a larger number from a smaller number, because you cannot calculate negative numbers in binary, you'll only get 0 when borrowing.
		- if there are multiple -1 subtraction, you have to do the leftmost one first
-  Multiplication:  
	- how to do it: https://www.youtube.com/watch?v=QW0XNZPyWUk
	- when add a 0 to a binary number you multiply it by 2, so if you give 3 then by 8 and so on
	- when you multiply two numbers together, you take one of the ones, and multiply it with each number in the top row, and you write it down, now you take this same number for example 0 1 0 1 and starting from the most right number just write it down leftwards and do this for each 1. after that's done you add all of these numbers together, could be 2 3 or what came out, and that's it.
- Division: 
	- how to do it: https://www.youtube.com/watch?v=j2Euknq3hc8
	-  can only be 1 if 1/1 or 1/0
	- can only be 0 if divided by 0/1 or 0/0
	- you are basically doing standard division, except when the the given number is divisible by divisor than you write a 1, and carry over the remainder, in binary form, and carry over the next number. and if it does not fit than you write a 0. and you do this until all the number from the number you want to divide is used up.

---
### Logic gates (AND, OR, NOT, XOR )
- Logic gates are fundamental building blocks of digital circuits that perform logical operations on one or more binary inputs to produce a binary output. They are represented by symbols and have specific truth table behaviours. Here's an explanation of the commonly used logic gates:
- statements
	- true or false
	- usually 1 represents true, and 0 represents false
	- also the fact that a statement is 0 basically means it cannot be 1
	- the inputs of Logic gates is call **operands**
- AND Gate:
	- Behaviour: The output of an AND gate is true (1) only when both of its inputs are true (1). Otherwise, the output is false (0).
	A   B   Output
	0   0     0
	0   1     0
	1   0     0
	1   1     1
- Or Gate:
	- Behaviour: The output of an OR gate is true (1) if at least one of its inputs is true (1). It produces a false (0) output only when both inputs are false (0).
	A   B   Output
	0   0     0
	0   1     1
	1   0     1
	1   1     1
- NOT Gate:
	- Behaviour: The NOT gate, also known as an inverter, has a single input and produces the complement of the input. It negates or reverses the input value. If the input is true (1), the output is false (0), and vice versa.
	Input   Output
	 0        1
	 1        0
-  XOR Gate:
	- Behaviour: The XOR gate, or exclusive OR gate, produces a true (1) output when the number of true inputs is odd. It returns false (0) when the number of true inputs is even.
	A   B   Output
	0   0     0
	0   1     1
	1   0     1
	1   1     0

---
### basics of Boolean algebra
- negation
	- not 0 = 1   not 1 = 0 
	- you can negate a variable by writing a vertical line above it
- The connection between 0 and 1
	- 0 + 0 = 0   0 + 1 = 1   1 + 0 = 1   1 + 1 = 1
	- 0 * 0 = 0   0 * 1 = 0   1 * 0 = 0   1 * 1 = 1
- connection between a variable and a value
	- A+0 = A
	- A+1 = 1
	- A * 0 = 0
	- A * 1 = 1
- operations with the same variable
	- A+A+...+A = A
	- A * A * A... * A = 1
	- not A + A = 1
	- not A * A = 0
	
---
### Role of mathematical logic in informatics
- Mathematical logic is the foundation of informatics, so it is very crucial
- It has crucial role in the followings
	- defining and analysing formal languages,
	- logic. Boolean algebra is extensively used in digital logic design
	- binary number system is the backbone of informatics
	- quantum computers use qubits which can even have two states at the same time
	- all of these ideas, first was developed in math
	
---
### Storage of digital images, image formats and their characteristics (raster and vector)
- Raster illustration:
	- An image is made up of a set of pixels arranged in columns and rows. The number of columns and rows given is the resolution of the image (e.g. 1920×1080, the image is 1920 pixels wide and 1080 pixels high). 
	- The colour of each pixel has to be stored. The colour quality of an image is determined by its colour depth, i.e. how many colours are selected from a palette of colours. the colour of the pixels.
	- When saving, information about the image in different formats (BMP, GIF, JPG, etc.), a lot of different things are  written to the header of the file including colour depth, so the actual space occupied is slightly larger than the actual size of the image.
	- 4 bit: 16 colours, 8 bit: 256 colours, etc.
	- The real solution is the RGB colour model, with 16 million colours. 
- vector image:
	- Another type of graphic type are vector images, which are used primarily for displaying drawings, geometric shapes that can be described by geometric formulas. The image file contains only the information needed to produce the image.
	- It's advantage is small space requirements, and flexible scaling, without any quality loss (since it isn't defined in a fixed coordinate system)
	- Vector graphics images are better quality, more editable and take up less space, but they are not suitable for real life images.
- some image formats:
	- without compression:
		- BMP
		- TIFF 
		- RAW - basically original file, clean, very large size
	- with compression:
		- JPEG - more aggressive, lossy
		- PNG - less loss in image quality
		- GIF 
		
---
### Ways of colour coding
- RGB 
	- In the RGB colour system, colours are created by adding the three primary colours red, green, blue. This is an additive colour mixing. This type of colour mixing system is based on the emitted or perceived light and can only be created by light-emitting devices (e.g. monitors). If all three colours are projected in "maximum quantity", white light is displayed, otherwise black.
	- 3 bytes are used, 1 for each colour, which sets how much of each colour should be added (i.e.: 255 255 255 is pure white)
	- 3 bytes are 24 bit, so there's 16 million+ colours possible with this system
- CMYK:
	- When printing coloured images, the CMYK model is used. Unlike RGB, this is not additive but subtractive colour mixing.
	- Consists of cyan, magenta, yellow, and black
	- it consists of 4 byte, which is 32 bit 
	
---
### The storage of digital audio, formats, and their characteristics.
- FLAC (Free Lossless Audio Codec) - lossless
- WAV (Waveform Audio File Format) - lossless
- MP3 (MPEG-1/2 Audio Layer 3) - lossy (128-192-256-320 kbit/s)
- AAC (Advanced Audio Coding) - lossy
- AC3 (Dolby Digital) - DVDs, Blu-rays
- MID (MIDI - Musical Instrument Digital Interface) - digital instruments (e.g., piano)
