# 编译可执行程序

# 工具链
CPP = g++
RM = rm -f
STRIP = strip

# 头文件路径
INC +=  -I./
# 第三方库
EXTLIBS = -lgtest  -lgmock -lgmock_main

# 编译选项
CFLAGS += -Wall -O2 -Os -g $(INC)

# 系统库
LDFLAGS +=  -lpthread


# 需要编译的文件 
SRCPATH = .
SOURCE += $(SRCPATH)/foo_unittest.cpp


EXE_OBJS = $(patsubst %.c,%.o,$(patsubst %.cpp,%.o,$(SOURCE)))

TARGET = ./test

all:$(TARGET)

$(TARGET):$(EXE_OBJS) $(EXTLIBS)
	$(CPP) -o $@ $^  $(LDFLAGS)

.cpp.o:
	$(CPP) -c $(CFLAGS) $^ -o $@

clean:
	$(RM) $(TARGET) $(EXE_OBJS)
