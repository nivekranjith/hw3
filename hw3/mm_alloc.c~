/*
 * mm_alloc.c
 *
 * Stub implementations of the mm_* routines. Remove this comment and provide
 * a summary of your allocator's design here.
 */

#include "mm_alloc.h"

#include <stdlib.h>

/* Your final implementation should comment out this macro. */
#define MM_USE_STUBS



void* mm_malloc(size_t size)
{

 s_block_ptr *curr,*head ;
void *addr =NULL;
static int i =0 ;
(*curr) = NULL;

if(size ==0 )
return(NULL) ;

if((*curr) ==NULL)
{
addr = NULL ;
}
if((*curr)->free!= 1 && size<= (*curr)->size)
{
   (*curr)->free =1 ;
   addr = (*curr)->ptr ;

}

while((*curr) != NULL)
{
  
if((*curr)->free!= 1 && size<= (*curr)->size)
{
   (*curr)->free =1 ;
   addr = (*curr)->ptr ;

}

(*curr) = (*curr)->next ;
}
 addr = (*curr)->ptr;



(*curr) = (*curr)->next ;
addr = sbrk(size) ;

if (addr == (void *)-1)
    {
      printf("Error : sbrk() failed\n");
      return (NULL);
    }

if(i==0)
(*curr) = NULL ;

(*curr)->size =size ;
(*curr)->ptr =addr ;
i++ ;
return(addr) ;
}





void* mm_realloc(void* ptr, size_t size)
{
#ifdef MM_USE_STUBS
    void *cpy ;

cpy = malloc(size) ;
memcpy(cpy , ptr , size) ;

return(cpy) ;


#else
#error Not implemented.
#endif
}

void mm_free(void* ptr)
{
#ifdef MM_USE_STUBS

s_block_ptr *curr,*head,*tmp ;
int inList = 0 ; ;
(*curr) = NULL ;
   
  if (ptr == NULL)
    return ;


while((*tmp)->ptr != ptr && tmp!= NULL)
     (*tmp) = (*tmp)->next ;
if((*tmp)->ptr != ptr)
    inList = 1;

  if (inList == 1)
    return ;
  while (ptr != (*tmp)->ptr && (*tmp) != NULL)
    (*tmp) = (*tmp)->next;
  if ((*tmp)->free != 1)
    return ;
 (*tmp)->free != 1 ;
  if ((*tmp) != NULL)
    {
      if ((*tmp)->next->free != 1 &&
      (*tmp)->next->ptr != (*tmp)->ptr)
    {
      if ((*tmp)->ptr > (*tmp)->next->ptr)
      (*tmp)->ptr =(*tmp)->next->ptr;
      (*tmp)->size += (*tmp)->next->size;
      (*tmp)->next = (*tmp)->next->next;
    }
    }
#else
#error Not implemented.
#endif
}
