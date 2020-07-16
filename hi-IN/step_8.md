## एक ही समय में दो धुन बजाना

संगीत में अक्सर एक दोहराव वाला ट्रैक होता है, जिसमें शीर्ष पर एक अलग राग बजाया जाता है। अब तक Sonic Pi में आपने एक धुन बजाई है। आइए एक ही समय में दो धुनों को बजाने की कोशिश करें!

- एक न​ए बफर टैब पर क्लिक करें।

2. जिस कोड को हम एक ही समय में दो धुनों को बजाने के लिए उपयोग करते हैं, उसे `in_thread do` और `end` के बीच होना चाहिए।

3. `in_thread do` के नीचे, अपनी धुन टाइप करें। यहाँ मैंने अपने बैकिंग ट्रैक के लिए एक नमूने का उपयोग किया है:
    
    ```ruby
    in_thread do
      loop do
        sample :loop_amen
        sleep 1.753
      end
    end       
    ```
    
    यह पहला 'thread' आपके संगीत के माधुर्य का काम करेगा। नीचे, आप अपने बैकिंग ट्रैक या बेसलाइन के लिए कोड टाइप कर सकते हैं।

4. टाइप करें:
    
    ```ruby
    in_thread do
      16.times do
        play 75
        sleep 1.753
        play 74
        sleep 0.25
      end
    end 
    ```

5. अब **play** दबाएँ और आपको एक ही समय में दोनों थ्रेड्स सुनाई देना चाहिए।