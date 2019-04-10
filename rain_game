; Noah Baculi 2012
; NetLogo
; University of Oregon Summer Enrichment Program

breed [people person]
breed [waters water]
breed [monsters monster]
breed [upper-missiles upper-missile]
breed [middle-missiles middle-missile]
breed [lower-missiles lower-missile]

to setup
  ca
  create-people 1
  ask people [
    set shape "person"
    set color yellow
    set size 2
    setxy random-xcor -4]
  
  create-waters Number_of_Raindrops
  ask waters [
    set shape "drop"
    set color blue - 1
    setxy random-xcor 15]
  
  create-monsters 1
  ask monsters [
    set shape "monster"
    set size 10
    setxy random-xcor 14]
  
  create-upper-missiles 1
  ask upper-missiles [
    set shape "upper missile"
    set size 7
    setxy 28 7.5
    kill-people]
  
  create-middle-missiles 1
  ask middle-missiles [
    set shape "middle missile"
    set size 8.5
    setxy 27.5 0
    kill-people]
  
  create-lower-missiles 1
  ask lower-missiles [
    set shape "lower missile"
    set size 7
    setxy 28 -7.5
    kill-people]
  
    
  ask patches [set pcolor sky - 1]


end

to go
  ask waters [
    kill-people
    fd Speed_of_Drops]
  
  tick
end

to move [ new-heading ]
  ask people
  [
    set heading new-heading
    fd Step_Size]
end

to jerk [ new-heading ]
  ask monsters
  [
    set heading new-heading
    fd Step_Size / 2
    kill-people]  
end

to head-upper [new-heading]
  ask upper-missiles
  [
    set heading new-heading 
    fd Speed_of_Upper_Missile
    kill-people]
end

to head-middle [new-heading]
  ask middle-missiles
  [
    set heading new-heading 
    fd Speed_of_Middle_Missile
    kill-people]
end

to head-lower [new-heading]
  ask lower-missiles
  [
    set heading new-heading 
    fd Speed_of_Lower_Missile
    kill-people]
end

to kill-people
  let prey one-of people-here                    ;; grab a random sheep
  if prey != nobody                              ;; did we get one?  if so,
    [ ask prey [ die ]]  
end
