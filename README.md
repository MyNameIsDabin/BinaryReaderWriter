# BinaryReaderWriter
바이너리 데이터로 파일을 읽고 쓰는 기능의 클래스. 별도의 라이브러리가 필요하지 않음.

<pre><code>
#include "BinaryWriter.h"
#include "BinaryReader.h"

using namespace std;

int main(void)
{
	BinaryWriter output("save.dat");
	output.writeInt(123);
	output.writeFloat(2.5f);
	output.writeDouble(8.2f);
	output.writeString("TEST");
	output.writeShort(5);
	output.writeString("¿ì³¢³£");
	output.writeInt(8);
	output.close();

	BinaryReader input("save.dat");
	int v1 = input.readInt();
	float v2 = input.readFloat();
	double v3 = input.readDouble();
	string v4 = input.readString();
	short v5 = input.readShort();
	string v6 = input.readString();
	int v7 = input.readInt();
	input.clear();

	cout << v1 << v2 << v3 << v5 << v6 << v7 << endl;

	return 0;
}
</code></pre>
