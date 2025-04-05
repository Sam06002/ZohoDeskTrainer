# Zoho Desk AI Training Bot

An intelligent system that uses DeepSeek AI to automatically predict and assign departments for support tickets in Zoho Desk.

## Features

- AI-powered department prediction using DeepSeek R1 Lite
- Automated training data collection
- Daily updates for new training data
- Agent feedback tracking and learning
- Model retraining and version control
- Comprehensive audit trail

## Project Structure

```
ai-dept-trainer/
├── Data_Collection/
│   ├── Collect_Historical_Data.deluge
│   ├── Daily_Training_Update.deluge
│   └── Feedback_Handler.deluge
├── AI_Integration/
│   ├── DeepSeek_Predictor.deluge
│   ├── Model_Retrain.deluge
│   └── Export_For_ML.deluge
└── Setup_Instructions.md
```

## Setup Instructions

1. **Create Required Modules in Zoho Desk**:
   - `AI_Training_Data`:
     - TicketID (Text)
     - EmailContent (Long Text)
     - AI_Prediction (Picklist)
     - AI_Reason (Long Text)
     - Final_Department (Picklist)
     - Agent_Notes (Long Text)
     - Feedback_Type (Picklist)
     - Model_Version (Text)

   - `AI_Audit_Log`:
     - Timestamp (DateTime)
     - TicketID (Text)
     - ModelVersion (Text)
     - Prediction (Text)
     - FinalDecision (Text)
     - AgentID (Lookup)

2. **Configure Environment**:
   - Store your DeepSeek API key in a secure configuration
   - Set up environment variables for sensitive data
   - Configure email notifications for ML team

3. **Deploy Scripts**:
   - Import all Deluge scripts into Zoho Desk
   - Set up workflow triggers for ticket creation
   - Schedule daily updates and model retraining

## Usage

1. **Initial Setup**:
   - Run `Collect_Historical_Data.deluge` once to gather initial training data
   - Configure department picklist values
   - Set up workflow triggers

2. **Daily Operations**:
   - New tickets are automatically processed by AI
   - Agents can provide feedback through `Feedback_Handler.deluge`
   - Training data is updated daily

3. **Model Management**:
   - Monthly retraining using `Model_Retrain.deluge`
   - Version control for model updates
   - Audit trail for all predictions

## Security

- Store API keys in secure configuration
- Use environment variables for sensitive data
- Implement proper access controls
- Regularly audit system logs

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, please:
1. Check the documentation
2. Open an issue on GitHub
3. Contact the development team
