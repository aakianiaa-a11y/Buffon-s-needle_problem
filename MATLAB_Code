%/. This code is created by Arash Kiani which simulates the Buffon's
%needle. It is better to run the cod for several time to appproach the
%desired rezult (pi number = 3.14).

clear;
clc;
close all;
%% --------- Initializing the parameters ---------------------------
L = 1;                  %% Length of the needles
t = L;
axnum = 18;             %% It would be better to enter an even number
needlenum = 15*axnum;
Theta = zeros(1,needlenum);
n = 0;
%% -------- Initializing the plot tools------------------
f = figure;
% f.WindowStyle = 'modal';
f.Name = 'Buffon''s needle teas';
% f.NumberTitle = 'off';
rectangle('Position',[0 0 axnum*t axnum*t],'Curvature',0.05,'LineWidth',2,'EdgeColor','c','FaceColor',[150/255 150/255 150/255]);
hold on
xlim([-1 axnum*t+1]);
ylim([-1 axnum*t+1]);
axis equal
ax1 = gca;                   % gca = get current axis
ax1.YAxis.Visible = 'off';   % remove y-axis
ax1.XAxis.Visible = 'off';   % remove x-axis

xdata = t*axnum*rand(1,needlenum);
ydata = t*axnum*rand(1,needlenum);
lines = linspace(0,axnum*t,axnum);


%% ------ Building the table of the test ----------
 for i =1:axnum-1
    plot(i*ones(1,axnum)*t,lines,'c','LineWidth',1);
    hold on
 end
 
 %% ------- Distribution the needles randomly -----------
 r = zeros(1,needlenum);
 for j = 1:needlenum
    plot(xdata(1,j),ydata(1,j),'ok','MarkerFaceColor','k','MarkerEdgeColor','w','MarkerSize',4);
    hold on
    Theta(1,j) = 90*rand; 
    needleplot(xdata(1,j),ydata(1,j),L,Theta(1,j));
 end
 
 %% -------------Decision loop---------------
 for k = 1:needlenum
     if any(0:axnum*t == xdata(1,k))
         n = n+1;
     elseif xdata(1,k)-round(xdata(1,k))<0
         if xdata(1,k) + 0.5*L*cosd(Theta(1,k)) >= round(xdata(1,k))
             n = n+1;
         end
     elseif xdata(1,k)-round(xdata(1,k))>0
         if xdata(1,k) - 0.5*L*cosd(Theta(1,k)) < round(xdata(1,k))
             n = n+1;
         end
     end
 end
 
 %% -------------Plotthe rezult ----------------- 
Pi_num = (2*L*needlenum)/(t*n);    
title(['Pi = ' num2str(Pi_num) '   ,   t = L   ,   n_{total} = ' num2str(needlenum) '   ,   n_{collision} = ' num2str(n)]);


%% ----------- Function to plot the line -----------
function needleplot(xCenter,yCenter,length,Theta)
x1 = xCenter-0.5*length*cosd(Theta);
x2 = xCenter+0.5*length*cosd(Theta);
y1 = yCenter-0.5*length*sind(Theta);
y2 = yCenter+0.5*length*sind(Theta);
plot([x1 x2],[y1 y2],'k','LineWidth',2);
hold on
end
