# player-detection
Football (or soccer) player detection in YOLOv11 using supervision to label the output

Achieves 90%+ accuracy on images



### Issues
"Flickering" when testing videos: If the confidence threshold is too high (~50%) you may get noticeable flickering as some of the frames have incorrect detections
This may be partly due to how the model was originally trained, which involved using players with uniform colours different from what the uniform colours in my test video.
In the future I want to look into a training method that might be more agnostic to the uniform colours

Goalie double classification: Currently, the goalie has a tendency to be classified as both player and goalie. This seems to be because of the previously mentioned uniform colours, where the original
uniform colours had lime green as the player colours, but my test video used lime green as goalie colours. Again, a somewhat colour agnostic detection model would help with this.

Alternatively, I could use colour averaging to group the players, this way I can detect if many players have 1 colour, letting me know that only players wear this colour, so I can block the goalie
from being detected as a player
