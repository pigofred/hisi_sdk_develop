# Hisilicon mpp sample Makefile

include ../Makefile.param

# target source
SRC  := $(wildcard *.c) 
OBJ  := $(SRC:%.c=%.o)
MPI_LIBS := $(REL_LIB)/libmpi.a
MPI_LIBS += $(REL_LIB)/libhdmi.a
MPI_LIBS += $(REL_LIB)/libtde.a
TARGET := $(OBJ:%.o=%)
.PHONY : clean all

all: $(TARGET)

$(TARGET):%:%.o $(COMM_OBJ)
	$(CC) $(CFLAGS) -lpthread -lm -o $@ $^ $(MPI_LIBS) $(AUDIO_LIBA) $(JPEGD_LIBA)  

clean:
	@rm -f $(TARGET)
	@rm -f $(OBJ)
	@rm -f $(COMM_OBJ)

cleanstream:
	@rm -f *.h264
	@rm -f *.jpg
	@rm -f *.mjp
	@rm -f *.mp4
