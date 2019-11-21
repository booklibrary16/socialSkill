
          int index1_19[] = new int[]{0,3,3,5,4,4,3,5,5,4,3,6,6,8,8,7,7,9,8,8};
          int index20_90[] = new int[]{0,0,6,6,5,5,5,7,6,6};
          int and = 3;
          int hundred = 7;
          int thousand = 8;
          int sum = 0;
          for(int i=1;i<1000;i++)
          {
              if(((i/100) > 0)&&((i%100)>0))
              {
                  sum+=index1_19[i/100]+hundred+and;
                  if((i%100)<20)
                  {
                      sum+=index1_19[i%100];
                  }
                  else
                  {
                      sum+=index1_19[(i%10)]+index20_90[((i%100)/10)];
                  }
              }
              else if(((i/100) > 0)&&((i%100)==0))
              {
                  sum+=index1_19[i/100]+hundred;
              }
              else if(((i/100) == 0))
              {
                  if((i%100)<20)
                  {
                      sum+=index1_19[i%100];
                  }
                  else
                  {
                      sum+=index1_19[(i%10)]+index20_90[((i%100)/10)];
                  }
              }

          }
          sum+=index1_19[1]+thousand;
          System.out.println(sum);
       }
