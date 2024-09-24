//基于二进制而实现的一个非常神金的加密程序

#include <iostream>
#include <vector>
#include <string>
#include <bitset>
#include <windows.h>

class encipher_bot
{
public:
    encipher_bot(std::string,std::string,std::string);
    encipher_bot();
    ~encipher_bot();

    void strToX();
    void XToStr();
    void print(int);
    void reset(std::string,std::string);
    std::vector<std::string> get(int);

private:
    std::string str_0;
    std::string str_1;
    std::string str_text;
    std::vector<std::string> str_encrypted;
    std::vector<std::string> str_decode;
};

encipher_bot::encipher_bot(std::string str_t,std::string str_1_ = "s",std::string str_0_ = "b")
{
    this->str_0 = str_0_;
    this->str_1 = str_1_;
    this->str_text = str_t;
}

encipher_bot::encipher_bot() {}

encipher_bot::~encipher_bot() {}

void encipher_bot::strToX()
{
    for(size_t i = 0; i < this->str_text.size(); i++)
    {
        std::bitset<8> bits(this->str_text[i]);
        for(int j = 7; j >= 0; j--)
        {
            str_encrypted.push_back(bits[j] ? this->str_1 : this->str_0);
        }
    }
}

void encipher_bot::XToStr()
{
    std::string temp;
    temp.clear();
    for(size_t i = 0; i < this->str_encrypted.size(); i += 8)
    {
        std::bitset<8> bits;
        for(int j = 0; j < 8 && (i+j) < this->str_encrypted.size(); j++)
        {
            if(this->str_encrypted[i + j] == this->str_1)
            {
                bits.set(7 - j);
            }
        }
        str_decode.push_back(temp = (static_cast<char>(bits.to_ulong())));
    }
}

void encipher_bot::print(int i = 0)
{
    if(i == 0)
        std::cout << this->str_text << std::endl;
    else if(i == 1)
    {
        for(std::string str : this->str_encrypted)
        {
            std::cout << str;
        }
        std::cout << "\n";
    }
    else if(i == 2)
    {
        for(std::string str : this->str_decode)
        {
            std::cout << str;
        }
        std::cout << "\n";
    }
}

void encipher_bot::reset(std::string str1,std::string str0)
{
    this->str_1 = str1;
    this->str_0 = str0;
}

std::vector<std::string> encipher_bot::get(int n = 1)
{
    if(n)
    return this->str_encrypted;
    else
    return this->str_decode;
}

int main()
{
    encipher_bot n("114514");
    n.reset("你好","sb");
    n.strToX();
    n.print(1);
    n.XToStr();
    n.print(2);
    Sleep(10000);
    return 0;
}
